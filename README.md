# test-repo

## Overview

This repository demonstrates automated README synchronization using GitHub Actions and Claude AI. The system automatically analyzes code changes from the last 7 days and creates pull requests to update documentation accordingly.

## Features

### 🤖 Automated README Sync Workflow

The repository includes a comprehensive GitHub Actions workflow (`hi.yml`) that:

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
- **Smart Skip Logic**: Automatically skips if no commits are found in the analysis period

## Setup Requirements

To use this workflow in your repository:

1. **Claude API Key**: Add `ANTHROPIC_API_KEY` to your repository secrets
2. **Permissions**: Ensure the workflow has `contents: write` and `pull-requests: write` permissions
3. **GitHub CLI**: The workflow uses `gh` commands for PR creation and management
4. **Repository Access**: Workflow requires full git history access (`fetch-depth: 0`)

## How It Works

1. **Trigger**: When a PR is opened/updated, the workflow activates
2. **Analysis**: Git history from the last 7 days is examined with comprehensive tooling
3. **Processing**: Claude analyzes changes and determines necessary README updates
4. **Branching**: A new timestamped branch is created from the main branch
5. **Documentation**: Updated README content is committed to the new branch
6. **Review**: A pull request is opened for human review of the documentation changes

## Workflow Configuration

The workflow is configured with:

- **Timeout**: 45 minutes for complex analysis tasks
- **Comprehensive Tools**: Access to full git command suite, file operations, and GitHub CLI
- **Enhanced Branch Handling**: Explicit checkout of default branch with verification
- **Robust Git Operations**: Status checks, branch verification, and improved error handling
- **Dynamic Environment**: Uses repository-specific default branch references
- **Advanced Permissions**: ID token write for secure operations

### Key Technical Features

- **Full History Access**: `fetch-depth: 0` ensures complete git history analysis
- **Dynamic Branch Detection**: Uses `github.event.repository.default_branch` for consistency
- **Comprehensive Tool Access**: Over 15 different git and GitHub CLI commands available
- **Error Recovery**: Built-in validation and pre-flight checks
- **Environment Variables**: Dynamic branch naming and date calculations

## Recent Activity

### Repository Timeline
- **Initial Setup**: Repository created with basic README
- **Workflow Development**: Added sophisticated GitHub Actions workflow for automated documentation
- **Enhanced Git Operations**: Improved branch handling and error recovery
- **Comprehensive Documentation**: Created detailed workflow documentation and setup guides

The repository demonstrates a complete automated documentation system that continuously maintains README accuracy as the codebase evolves, providing a reference implementation for teams looking to automate their documentation workflows.