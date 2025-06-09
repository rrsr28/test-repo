# test-repo

## 🤖 Automated README Synchronization System

This repository features an intelligent, AI-powered documentation system that automatically maintains README currency through sophisticated analysis of code changes.

## 🌟 Overview

The **Claude README Sync** system leverages GitHub Actions and Claude AI to:

- **📊 Analyze Recent Changes**: Automatically examines the last 7 days of commits on the main branch
- **🧠 AI-Powered Updates**: Uses Claude AI to intelligently generate documentation updates based on code changes
- **🔄 Automated PR Creation**: Creates separate pull requests for documentation updates, maintaining clean separation
- **🛡️ Safety Features**: Prevents circular updates and ensures clean base analysis by excluding triggering PR changes

## ⚙️ How It Works

### Trigger Mechanism
The system activates automatically when:
- A new pull request is **opened**
- An existing pull request is **synchronized** (updated with new commits)

### Analysis Process
1. **Clean Base Checkout**: Checks out the main branch state *before* the triggering PR using `github.event.pull_request.base.sha`
2. **7-Day Analysis**: Examines all commits merged to main in the last 7 days
3. **Change Detection**: Identifies modified files, commit messages, and code differences
4. **AI Analysis**: Claude AI analyzes changes and determines if README updates are needed
5. **Separate PR Creation**: If updates are needed, creates a new branch and pull request with *only* README changes

### Safety Features
- **PR Isolation**: Excludes changes from the triggering PR to prevent circular updates
- **Clean Base Analysis**: Uses base SHA for accurate main branch analysis without PR changes
- **Branch Separation**: Documentation updates are isolated in separate branches
- **No-Change Detection**: Automatically skips when no updates are needed

## 🔧 Technical Implementation

### Workflow Configuration
- **File**: `.github/workflows/hi.yml` (208 lines)
- **Trigger**: `pull_request` events (`opened`, `synchronize`)
- **Runtime**: Ubuntu Latest
- **Timeout**: 45 minutes maximum

### Required Permissions
```yaml
permissions:
  contents: write          # Read repository and create branches
  pull-requests: write     # Create and manage pull requests  
  id-token: write         # Authentication for Claude integration
```

### Environment Variables
- **`BASE_SHA`**: Main branch commit before triggering PR
- **`SINCE_DATE`**: 7 days ago (ISO 8601 format)
- **`COMMIT_COUNT`**: Number of commits found in analysis period
- **`BRANCH_NAME`**: Unique timestamp-based branch name (`readme-sync-YYYYMMDD-HHMMSS`)

### Required Secrets
- **`ANTHROPIC_API_KEY`**: API key for Claude AI integration
- **`GITHUB_TOKEN`**: Automatically provided by GitHub Actions

## 🛠️ Allowed Tools
The Claude AI integration has access to:
- **Bash**: Full shell command access including git operations
- **git**: Version control operations (log, diff, add, commit, push, etc.)
- **gh**: GitHub CLI for pull request creation and management
- **View**: File reading capabilities for analysis
- **Glob**: File pattern matching for codebase exploration
- **Grep**: Content searching within files
- **Batch**: Batch operations for efficient processing
- **Edit**: File editing capabilities for README updates

## 📋 Usage

### For Developers
When you create or update a pull request:

1. **Automatic Trigger**: The README sync workflow activates automatically
2. **Background Analysis**: Claude analyzes recent main branch changes (excluding your PR)
3. **Documentation Updates**: If changes warrant documentation updates, a separate PR is created
4. **Independent Review**: The documentation PR can be reviewed and merged independently

### Manual Triggering
The workflow runs automatically, but you can also:
- Close and reopen a PR to retrigger analysis
- Push new commits to an existing PR to trigger synchronization

### Branch Naming
Documentation update branches follow the pattern: `readme-sync-YYYYMMDD-HHMMSS`

## 🎯 Benefits

### For Development Teams
- **🔄 Always Current**: Documentation stays synchronized with code changes
- **⚡ Zero Overhead**: No manual documentation maintenance required
- **🎯 Focused Reviews**: Documentation updates are isolated for easier review
- **🚀 Consistent Quality**: AI-powered analysis ensures comprehensive coverage

### For Repository Users
- **📚 Accurate Documentation**: README always reflects the latest functionality
- **🔍 Change Visibility**: Clear documentation of new features and modifications
- **⏱️ Timely Updates**: Documentation updates happen automatically with code changes

## 🏗️ System Architecture

```
PR Creation/Update
        ↓
Analysis Trigger (GitHub Actions)
        ↓
Main Branch Checkout (Clean Base)
        ↓
7-Day Change Analysis
        ↓
Claude AI Processing
        ↓
README Update Generation
        ↓
Separate PR Creation
        ↓
Independent Documentation Review
```

This system represents a sophisticated approach to maintaining documentation currency through intelligent automation, ensuring that project documentation evolves seamlessly alongside the codebase.