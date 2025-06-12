# test-repo

A GitHub repository featuring automated documentation management powered by Claude AI.

## 🤖 Automated Documentation System

This repository implements an intelligent weekly README update system that analyzes code changes and maintains documentation automatically.

### Features

- **🔄 Weekly Analysis**: Automatically reviews the last 7 days of development activity
- **🧠 AI-Powered Updates**: Uses Claude Sonnet 4 to analyze changes and update documentation
- **📊 Comprehensive Tracking**: Analyzes commits, file changes, and code statistics
- **🔒 Secure Operations**: Uses official Anthropic Claude Code action with controlled permissions
- **🎯 Smart Updates**: Only modifies README.md when actual functional changes occur

## 📋 Current Workflow Configuration

### Weekly README Update (`claude-readme.yml` & `new2.yml`)

**Schedule**: Every Monday at 7:59 AM UTC
**Trigger**: Manual dispatch available with force update option

**Analysis Process**:
1. **Change Detection**: Reviews last 7 days of commits
2. **File Analysis**: Generates detailed analysis files for AI processing
3. **Smart Processing**: Uses Claude to analyze changes and update documentation
4. **PR Creation**: Automatically creates pull requests for documentation updates
5. **Cleanup**: Removes temporary analysis files

**Permissions**: 
- `contents: write` - for creating branches and commits
- `pull-requests: write` - for creating pull requests

## 🏗️ Repository Structure

```
.github/workflows/
├── claude-readme.yml    # Primary weekly README update workflow
├── new2.yml            # Secondary weekly README update workflow
README.md               # This file - automatically maintained
```

## 🔍 How It Works

1. **Scheduled Execution**: Workflows run weekly or can be manually triggered
2. **Git Analysis**: System analyzes commits, changed files, and code statistics
3. **Data Preparation**: Creates temporary analysis files for Claude processing
4. **AI Processing**: Claude analyzes changes and determines necessary documentation updates
5. **Documentation Update**: README.md is updated to reflect functional changes
6. **PR Workflow**: Changes are submitted via pull request for review
7. **Cleanup**: Temporary files are automatically removed

## 🛡️ Security & Reliability

- ✅ Uses official Anthropic Claude Code action
- ✅ Controlled tool permissions for Claude
- ✅ Automatic cleanup of temporary files
- ✅ Only modifies README.md, never other project files
- ✅ All changes based on actual git history analysis
- ✅ No third-party actions used

## 📈 Workflow Statistics

Recent activity shows active development of the automation system with comprehensive workflow management and cleanup operations.

---

**Last Updated**: 2025-06-12  
**Documentation System**: Claude AI-powered automation  
**Update Frequency**: Weekly (Mondays)