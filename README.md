# test-repo

An intelligent GitHub repository featuring automated documentation management powered by Claude AI.

## Features

### 🤖 Weekly Automated README Updates
This repository includes a sophisticated GitHub Actions workflow that analyzes development activity and maintains up-to-date documentation:

- **Schedule**: Runs every Monday at 4:30 AM UTC  
- **Analysis Period**: Reviews the last 7 days of commits and code changes
- **Smart Updates**: Creates pull requests only when meaningful changes are detected
- **AI-Powered**: Uses Claude Sonnet 4 to analyze code changes and update documentation intelligently

### 📋 Workflow Details

The automated README update workflow (`claude-readme.yml`) performs comprehensive analysis:

1. **Change Detection**: Analyzes commits from the past 7 days
2. **File Analysis**: Tracks all modified files and code changes (+additions/-deletions)
3. **Intelligent Updates**: Uses Claude AI to determine if README updates are needed
4. **PR Creation**: Automatically creates pull requests with detailed change summaries
5. **Clean Operations**: Removes temporary analysis files after completion

### 🔧 Workflow Configuration

```yaml
# Scheduled weekly runs
schedule:
  - cron: '30 13 * * *'  # Every Monday at 4:30 AM UTC

# Manual trigger option
workflow_dispatch:
  inputs:
    force_update:
      description: 'Force update even if no changes'
      type: boolean
      default: false
```

## Repository Structure

```
.github/workflows/
├── claude-readme.yml    # Weekly automated README sync workflow
README.md               # This file - automatically maintained
```

## How It Works

The automation workflow follows this process:

1. **Analysis Phase**: Examines the last 7 days of commits and generates detailed change reports
2. **AI Review**: Claude AI analyzes the changes to determine documentation relevance
3. **Update Phase**: If changes affect user-facing functionality, README.md is updated
4. **PR Creation**: Creates a pull request with detailed analysis and change summary
5. **Assignment**: Automatically assigns the PR to the repository owner for review

## Development

When working in this repository:

- **Automatic Documentation**: README updates happen automatically based on your code changes
- **Weekly Sync**: Changes are analyzed and documented every Monday
- **Manual Trigger**: You can manually trigger documentation updates if needed
- **No Manual Maintenance**: The README stays current without manual intervention

## Automation Details

- **GitHub Actions**: Powered by scheduled workflows with intelligent change detection
- **Claude AI Integration**: Uses `claude-sonnet-4-20250514` for content analysis and generation  
- **Smart Branching**: Creates separate branches for documentation updates
- **Comprehensive Analysis**: Tracks file changes, commit messages, and code statistics
- **Secure Operations**: Uses GitHub tokens and follows security best practices

*Last updated: 2025-06-13 (automatically maintained)*