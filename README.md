# test-repo

A GitHub repository featuring automated weekly documentation management with AI-powered analysis and updates.

## Features

### 🤖 Automated Weekly README Updates
This repository uses a sophisticated GitHub Actions workflow that automatically analyzes code changes and maintains documentation:

- **Schedule**: Runs every Monday at 4:30 AM UTC (configurable via cron)
- **Analysis Period**: Reviews the last 7 days of development activity  
- **Smart Analysis**: Uses Claude Sonnet 4 to analyze commits, file changes, and code diffs
- **Separate PRs**: Creates dedicated pull requests for documentation updates
- **Manual Trigger**: Supports on-demand execution via workflow dispatch

### 📋 Workflow Capabilities

The automated README workflow (`claude-readme.yml`) performs comprehensive analysis:

1. **Change Detection**: Analyzes commits from the past 7 days
2. **File Analysis**: Reviews modified files and generates detailed diffs
3. **AI Processing**: Uses Claude Sonnet 4 with restricted tool access for secure updates
4. **Documentation Updates**: Intelligently updates README.md based on actual code changes
5. **PR Management**: Creates timestamped branches and detailed pull requests
6. **Cross-Referencing**: Links documentation updates to analyzed changes

### 🔧 Technical Implementation

**Workflow Features:**
- **Timeout Protection**: 30-minute workflow timeout with 15-minute Claude processing limit
- **Permission Management**: Controlled access to repository contents and PR creation
- **Branch Strategy**: Creates unique timestamped branches for each update
- **Tool Restrictions**: Limited bash commands and secure git operations only
- **Cleanup System**: Automatically removes temporary analysis files

**Analysis Process:**
- Generates comprehensive change analysis files
- Creates detailed commit summaries and file change statistics  
- Produces full git diffs for AI analysis
- Provides fallback strategies for edge cases

## Repository Structure

```
.github/workflows/
├── claude-readme.yml   # Weekly automated README update workflow
README.md              # This file - automatically maintained weekly
```

## Automation Details

### Weekly Update Process
1. **Scheduled Execution**: Triggered every Monday at 4:30 AM UTC
2. **Change Analysis**: Reviews all commits from the past 7 days
3. **File Processing**: Analyzes modified files and generates statistics
4. **AI Analysis**: Claude Sonnet 4 processes changes and updates documentation
5. **PR Creation**: Generates detailed pull request with analysis summary
6. **Review Process**: Assigns PR to repository owner for review

### Manual Execution
The workflow can be manually triggered via GitHub's "Actions" tab with an optional force update parameter to bypass the "no changes" check.

### Security Features
- **Restricted Tool Access**: Limited to essential git and file operations
- **Secure Authentication**: Uses GitHub tokens for repository access
- **Controlled AI Access**: Anthropic API key stored as repository secret
- **Temporary File Management**: Analysis files are automatically cleaned up

## Development

This repository demonstrates automated documentation maintenance using AI analysis. The workflow creates separate documentation PRs to maintain a clean development history while ensuring documentation stays current with code changes.

**Last Updated**: 2025-06-15 (Weekly automated update)