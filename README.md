# Automated README Update System

A GitHub Actions workflow system that automatically analyzes weekly code changes and updates README documentation using Claude AI.

## Overview

This repository demonstrates an automated documentation system that:
- Analyzes code changes from the past 7 days
- Uses Claude AI to intelligently update README documentation
- Creates pull requests with detailed change summaries
- Maintains accurate and up-to-date project documentation

## Features

### 🤖 Automated Analysis
- **Weekly Scheduling**: Runs every Monday at 4:30 AM UTC
- **Manual Triggers**: Supports manual workflow dispatch with force update option
- **Comprehensive Analysis**: Tracks commits, file changes, and code statistics

### 📊 Change Detection
- Analyzes git history from the past week
- Generates detailed diff reports
- Counts additions, deletions, and modified files
- Creates structured analysis files for AI processing

### 🧠 AI-Powered Updates
- Uses Claude Sonnet 4 for intelligent documentation updates
- Analyzes code changes for meaningful documentation improvements
- Maintains existing documentation structure and tone
- Only updates sections relevant to actual code changes

### 🔄 Pull Request Automation
- Creates dedicated branches for each update
- Generates detailed PR descriptions with analysis summaries
- Auto-assigns repository owner for review
- Includes comprehensive change statistics

## Workflow Configuration

The system is configured via `.github/workflows/claude-readme.yml`:

```yaml
schedule:
  # Every Monday at 4:30 AM UTC
  - cron: '30 13 * * *'
```

### Required Secrets
- `ANTHROPIC_API_KEY`: API key for Claude AI integration
- `GITHUB_TOKEN`: Automatically provided by GitHub Actions

### Permissions
- `contents: write` - For creating commits and branches
- `pull-requests: write` - For creating pull requests

## How It Works

1. **Analysis Phase**: Collects git statistics and generates analysis files
2. **AI Processing**: Claude analyzes changes and updates documentation
3. **Change Detection**: Checks if README.md was modified
4. **PR Creation**: Creates pull request with detailed summary if changes exist
5. **Cleanup**: Removes temporary analysis files

## Recent Updates

**Last Updated**: 2025-06-19

### Recent Workflow Improvements (June 12, 2025)
- Enhanced error handling for repositories without week-old commits
- Improved diff generation with proper commit range syntax
- Added fallback strategies for analysis file generation
- Refined Claude prompt instructions for more precise updates
- Optimized temporary file management and cleanup

## Contributing

This system is designed to be self-maintaining. The AI will automatically update documentation based on code changes. Manual README updates should be made carefully to preserve the automated update structure.

## License

This project demonstrates automated documentation workflows and is provided as-is for educational and reference purposes.