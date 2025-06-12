# test-repo

A GitHub repository with advanced automated documentation management capabilities powered by Claude AI.

## 🤖 Automated Documentation System

This repository features a sophisticated weekly README update system that analyzes code changes and maintains documentation automatically.

### 📅 Weekly README Updates

- **Schedule**: Every Monday at 4:30 AM UTC (automated via GitHub Actions)
- **Analysis Period**: Reviews the last 7 days of development activity  
- **AI-Powered**: Uses Claude Sonnet-4 to analyze changes and update documentation
- **Pull Request Workflow**: Creates separate PRs for documentation updates with detailed analysis

### 🔧 Workflow Features

The automated system (`.github/workflows/claude-readme.yml`) includes:

- **Smart Analysis**: Examines commit history, file changes, and code diffs
- **Comprehensive Reporting**: Generates detailed analysis files for accurate updates
- **Change Detection**: Only creates PRs when meaningful changes are detected
- **Fallback Strategies**: Handles edge cases like new repositories or minimal changes
- **Clean Automation**: Automatically cleans up temporary analysis files

### 📊 Analysis Capabilities

The workflow generates multiple analysis files:
- `detailed_analysis_temp.txt` - Complete commit and file change analysis
- `weekly_changes_temp.diff` - Full git diff of code changes
- `recent_commits_temp.txt` - Formatted commit messages with metadata
- `changed_files_temp.txt` - List of all modified files

## 🚀 Getting Started

This repository automatically maintains its documentation. When you:
1. Make code changes throughout the week
2. The Monday automation will analyze all changes
3. If significant updates are needed, a PR will be created
4. Review and merge the documentation PR to keep README current

## 🔄 Manual Triggers

You can also trigger the documentation update manually:
- Navigate to Actions tab → "Weekly README Update Original"
- Click "Run workflow" and optionally enable "Force update even if no changes"

## 📈 Recent Activity

*Last updated: 2025-06-12*

The repository has been actively developed with 103 commits analyzed in the past week, focusing primarily on refining and optimizing the automated documentation workflow system.