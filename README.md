# test-repo

## Automated README Synchronization System

This repository features an automated documentation system that analyzes code changes and maintains up-to-date README files based on recent development activity.

### 🔄 How It Works

The README synchronization system automatically:

- **Analyzes the last 7 days** of code changes whenever a pull request is opened or updated
- **Creates separate pull requests** for documentation updates to maintain clean change separation
- **Uses AI-powered analysis** via Claude Code Action to understand code changes and update documentation accordingly
- **Prevents conflicts** by working on separate branches for documentation updates

### 🛠️ Technical Details

#### Workflow Configuration
- **Trigger**: Pull request events (opened, synchronize)
- **Runner**: Ubuntu Latest with full repository history
- **Permissions**: Contents write, pull requests write, ID token write
- **Timeout**: 45 minutes maximum execution time

#### AI Integration
- **Powered by**: Anthropic Claude via `anthropics/claude-code-action@beta`
- **Analysis Tools**: Git history analysis, file content examination, pattern recognition
- **Allowed Operations**: Git operations, file editing, branch management, PR creation

#### Branch Management
- **Strategy**: Creates timestamped branches (format: `readme-sync-YYYYMMDD-HHMMSS`)
- **Base**: Always works from `main` branch
- **Cleanup**: Automatic through PR merge/close workflows

### 📋 Features

- **7-Day Change Analysis**: Automatically reviews commits, file changes, and code modifications
- **Smart Documentation Updates**: Updates multiple README sections (installation, usage, API docs, features)
- **Convention Following**: Maintains existing structure, tone, and formatting standards
- **Automated Pull Requests**: Creates properly formatted PRs with detailed change summaries
- **Cross-PR Comments**: Updates triggering PR with analysis results and documentation links

### 🚀 Usage

The system operates automatically - no manual intervention required:

1. **Open or update a pull request** → System triggers analysis
2. **7-day change analysis runs** → Examines recent commits and modifications  
3. **README assessment occurs** → Determines if documentation updates are needed
4. **Separate PR created** → Documentation changes proposed in clean PR
5. **Original PR updated** → Comment added with analysis results and links

### ⚙️ Configuration

#### Environment Variables
- `ANTHROPIC_API_KEY`: Required for Claude AI integration
- `GITHUB_TOKEN`: Automatically provided for repository operations

#### Allowed Tools
- Git operations (config, checkout, branch, status, log, diff, add, commit, push)
- File operations (view, glob, grep, edit)
- GitHub API operations (branch creation, PR creation, comments)

This automated system ensures documentation stays current with minimal developer overhead while maintaining high-quality, comprehensive README files.
