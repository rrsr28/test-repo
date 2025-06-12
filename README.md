# test-repo

An automated documentation management system powered by Claude AI and GitHub Actions.

## 🤖 Overview

This repository demonstrates intelligent, automated README maintenance using Claude AI. It analyzes code changes weekly and updates documentation to keep it accurate and current without manual intervention.

## ✨ Features

### 📚 Automated Weekly README Updates
- **Smart Analysis**: Reviews 7 days of commit history and code changes
- **AI-Powered Writing**: Uses Claude Sonnet 4 to generate meaningful documentation updates
- **Pull Request Workflow**: Creates separate PRs for documentation changes with detailed analysis
- **Scheduled Execution**: Runs every Monday at 8:35 AM UTC via cron schedule
- **Manual Trigger**: Supports on-demand updates through workflow dispatch

### 🔄 Dual Workflow System
The repository includes two complementary GitHub Actions workflows:

#### `claude-readme.yml` - Weekly README Update Original
- Comprehensive weekly analysis and README synchronization
- Detailed commit analysis with statistics tracking
- Automated pull request creation with rich metadata
- Temporary file management and cleanup

#### `new2.yml` - Weekly README Update  
- Secondary workflow for reliability and redundancy
- Identical functionality with slight configuration differences
- Ensures consistent documentation maintenance

## 🏗️ Architecture

```
.github/workflows/
├── claude-readme.yml    # Primary weekly README update workflow
├── new2.yml            # Secondary weekly README update workflow
└── [legacy workflows removed]

README.md               # This file - automatically maintained
```

## 🚀 How It Works

1. **Weekly Trigger**: Workflows activate every Monday via cron schedule
2. **Change Analysis**: Git history from the last 7 days is analyzed
3. **File Tracking**: All modified files and code statistics are captured
4. **AI Processing**: Claude AI analyzes changes and updates documentation accordingly
5. **PR Creation**: New pull requests are created with detailed change summaries
6. **Cleanup**: Temporary analysis files are automatically removed

## 📊 Current Status

- **Last Updated**: 2025-06-12
- **Recent Activity**: 91 commits analyzed (2025-06-05 to 2025-06-12)
- **Files Modified**: 4 workflow files with 596 additions, 192 deletions
- **Workflow Status**: Fully operational with redundant systems

## 🛠️ Configuration

### Required Secrets
- `ANTHROPIC_API_KEY`: API key for Claude AI integration
- `GITHUB_TOKEN`: Automatically provided by GitHub Actions

### Workflow Parameters
- **Claude Model**: `claude-sonnet-4-20250514`
- **Timeout**: 15-30 minutes per workflow
- **Analysis Period**: 7 days rolling window
- **Branch Pattern**: `readme-update-YYYYMMDD-HHMMSS`

## 🔍 Recent Changes (Week of 2025-06-05)

This week saw major workflow reorganization:
- Replaced legacy `hi.yml` workflow with modern `claude-readme.yml` and `new2.yml` systems
- Implemented improved error handling and file management
- Added comprehensive pull request metadata and tracking
- Enhanced commit analysis and statistics generation
- Streamlined temporary file cleanup processes

## 🎯 Use Cases

This repository serves as:
- **Documentation Automation Demo**: Shows how AI can maintain technical documentation
- **GitHub Actions Template**: Reusable workflows for README management  
- **AI Integration Example**: Practical Claude AI implementation in CI/CD
- **Workflow Testing Ground**: Safe environment for testing documentation automation

## 📈 Benefits

- **Always Current**: Documentation stays synchronized with code changes
- **Zero Maintenance**: No manual README updates required
- **Intelligent Analysis**: AI understands context and makes meaningful updates
- **Audit Trail**: Full history of changes with detailed pull request records
- **Reliable Operation**: Redundant workflows ensure consistent execution

---

*This README is automatically maintained by Claude AI. Last analysis: 91 commits from 2025-06-05 to 2025-06-12*