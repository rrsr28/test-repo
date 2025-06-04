# test-repo

## Overview

This repository demonstrates automated README synchronization using GitHub Actions and Claude AI. The system automatically analyzes code changes from the last 7 days and creates pull requests to update documentation accordingly.

## Features

### 🤖 Automated README Sync Workflow

The repository includes a GitHub Actions workflow (`hi.yml`) that:

- **Triggers**: Automatically runs when pull requests are opened or updated
- **Analysis**: Examines the last 7 days of commits and file changes
- **Documentation**: Uses Claude AI to analyze changes and update the README
- **Pull Request Creation**: Creates separate PRs for README updates with comprehensive descriptions
- **Smart Branching**: Generates unique branch names with timestamps (format: `readme-sync-YYYYMMDD-HHMMSS`)

### Workflow Capabilities

- **Change Detection**: Identifies all files modified in the last 7 days
- **Commit Analysis**: Reviews commit messages and code changes
- **README Updates**: Automatically updates relevant sections (installation, usage, API docs, features)
- **PR Management**: Creates detailed pull requests with before/after comparisons
- **Cross-referencing**: Links new documentation PRs to triggering PRs

## Setup Requirements

To use this workflow in your repository:

1. **Claude API Key**: Add `ANTHROPIC_API_KEY` to your repository secrets
2. **Permissions**: Ensure the workflow has `contents: write` and `pull-requests: write` permissions
3. **GitHub CLI**: The workflow uses `gh` commands for PR creation

## How It Works

1. **Trigger**: When a PR is opened/updated, the workflow activates
2. **Analysis**: Git history from the last 7 days is examined
3. **Processing**: Claude analyzes changes and determines necessary README updates
4. **Documentation**: A new branch is created with updated README content
5. **Review**: A pull request is opened for human review of the documentation changes

## Workflow Configuration

The workflow is configured with:
- **Timeout**: 45 minutes for complex analysis
- **Tools**: Access to git commands, file operations, and GitHub CLI
- **Smart Skip**: Automatically skips if no commits are found in the analysis period

## Recent Activity

This repository was initialized with the automated README sync workflow on June 4, 2025. The workflow enables continuous documentation maintenance as the codebase evolves.