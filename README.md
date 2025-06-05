# test-repo

## Automated README Synchronization System

This repository features an intelligent, AI-powered documentation system that automatically maintains and updates the README based on code changes.

## Features

### 🤖 Automated Documentation
- **7-Day Analysis**: Automatically analyzes the last 7 days of repository changes
- **Smart Updates**: Uses Claude AI to intelligently update documentation based on code changes
- **Separate PR Creation**: Creates dedicated pull requests for documentation updates
- **Zero Manual Maintenance**: Documentation stays current without manual intervention

### 🔄 Workflow Automation
- **Pull Request Triggered**: Activates on PR open/synchronize events
- **Branch Management**: Automatically creates timestamped branches for README updates
- **Conflict Prevention**: Works on separate branches to avoid conflicts with main development
- **Comprehensive Analysis**: Reviews commits, file changes, and code modifications

### 🛠️ Technical Details

**Runtime Environment:**
- Runs on Ubuntu Latest
- Full repository history access (fetch-depth: 0)
- Comprehensive permissions for content and PR management

**AI Integration:**
- Claude Code Action (Beta) integration
- 45-minute timeout for complex analysis
- Extensive tool permissions for git operations and file management
- Direct prompt customization for specific analysis requirements

**Permissions:**
- `contents: write` - Repository content modification
- `pull-requests: write` - PR creation and management  
- `id-token: write` - Authentication token management

## Usage

The system operates automatically when:
1. Pull requests are opened or synchronized
2. Changes are detected in the last 7 days
3. Analysis determines README updates are beneficial

### Workflow Process

1. **Change Detection**: Analyzes commits from the past week
2. **File Analysis**: Reviews modified files and their impact
3. **AI Assessment**: Claude AI evaluates if documentation updates are needed
4. **Branch Creation**: Creates timestamped branch for README updates
5. **Content Generation**: Generates comprehensive documentation updates
6. **PR Creation**: Creates pull request with detailed analysis
7. **Original PR Notification**: Comments on triggering PR with update status

## Configuration

The system is configured via `.github/workflows/hi.yml` with:
- Automated scheduling and triggers
- Claude AI integration settings
- Git configuration and branch management
- Error handling and fallback mechanisms

### Environment Variables
- `ANTHROPIC_API_KEY`: Required for Claude AI integration
- `GITHUB_TOKEN`: Automatic GitHub authentication
- Dynamic branch naming with timestamps
- Commit count and date range tracking

This automated system ensures that documentation always reflects the current state of the codebase, making the repository more maintainable and accessible to contributors.