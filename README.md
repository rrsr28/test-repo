# test-repo

An automated documentation management system powered by GitHub Actions and Claude AI.

## 🤖 Automated README Management

This repository features a sophisticated automated documentation system that analyzes code changes and maintains up-to-date README content.

### Features

- **📅 Weekly Scheduled Updates**: Automated README updates every Monday at 8:35 AM UTC
- **🔍 Intelligent Analysis**: Reviews the last 7 days of commits and code changes
- **🤖 AI-Powered Content**: Uses Claude Sonnet 4 to generate accurate, contextual documentation
- **🔄 Pull Request Workflow**: Creates dedicated PRs for documentation changes with detailed analysis
- **🧹 Clean Automation**: Temporary analysis files are automatically cleaned up

### Active Workflows

#### 📚 Weekly README Update (`claude-readme.yml`)
- **Trigger**: Scheduled (Mondays at 8:35 AM UTC) + Manual dispatch
- **Analysis Period**: Last 7 days of development activity
- **AI Model**: Claude Sonnet 4 (claude-sonnet-4-20250514)
- **Timeout**: 15 minutes
- **Features**:
  - Comprehensive commit and file change analysis
  - Statistical summaries (+additions/-deletions)
  - Smart content updates based on actual code changes
  - Automated PR creation with detailed descriptions

#### 📚 Weekly README Update (`new2.yml`)
- **Duplicate workflow** with identical functionality to `claude-readme.yml`
- **Purpose**: Backup/testing workflow for reliability

### Repository Structure

```
.github/workflows/
├── claude-readme.yml    # Primary weekly README update workflow
├── new2.yml            # Secondary weekly README update workflow
README.md               # This file - automatically maintained
```

### How It Works

1. **Change Detection**: Analyzes commits from the past 7 days
2. **File Analysis**: Identifies modified files and generates diff statistics
3. **AI Analysis**: Claude AI processes changes and updates documentation accordingly
4. **PR Creation**: Creates pull requests with detailed change summaries
5. **Clean Up**: Removes temporary analysis files automatically

### Automation Statistics

- **Total Commits (Last 7 Days)**: 91 commits
- **Files Modified**: 4 files
- **Code Changes**: +596/-192 lines
- **Analysis Period**: 2025-06-05 to 2025-06-12

### Recent Development Activity

The repository has undergone significant workflow reorganization:
- **Workflow Migration**: Replaced old PR-triggered system with scheduled updates
- **Enhanced Automation**: Improved analysis capabilities and error handling
- **Code Cleanup**: Removed deprecated workflow files (hi.yml, hi2.yml, hi3.yml)
- **Documentation Reset**: README rebuilt from scratch based on current functionality

### Security & Reliability

- ✅ Uses official Anthropic Claude Code GitHub Action
- ✅ Scoped permissions (contents: write, pull-requests: write)
- ✅ Automatic cleanup of temporary files
- ✅ No third-party dependencies
- ✅ Secure token handling

## Last Updated

**2025-06-12** - Automated update based on weekly code analysis