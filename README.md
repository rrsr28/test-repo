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
- **Tools**: Access to comprehensive git commands, file operations, and GitHub CLI
- **Smart Skip**: Automatically skips if no commits are found in the analysis period
- **Enhanced Branch Handling**: Explicitly checks out the default branch and verifies git status
- **Robust Git Operations**: Includes status checks, branch verification, and improved error handling

## Latest Improvements

### Version 2.0 Enhancements (June 4, 2025)

The workflow has been enhanced with several key improvements:

#### 🔧 **Enhanced Git Operations**
- **Explicit Branch Checkout**: Uses `github.event.repository.default_branch` for consistent main branch detection
- **Pre-flight Checks**: Adds `git status` and `git branch` verification before operations
- **Improved Error Handling**: Better git command sequencing and error recovery

#### 🛠️ **Expanded Tool Access**
- **Additional Git Commands**: Enhanced allowed tools including status and branch verification
- **Refined PR Creation**: More specific GitHub CLI commands with explicit base branch handling
- **Better Workflow Context**: Improved environment variable usage for cross-step communication

#### 📋 **Workflow Reliability**
- **Consistent Branch References**: All git operations now use the repository's default branch
- **Enhanced Documentation**: More detailed step-by-step instructions in the direct prompt
- **Improved Validation**: Better verification of git state before performing operations

## Recent Activity

### June 4, 2025
- **Repository Initialization**: Created automated README sync workflow with Claude AI integration
- **Workflow Enhancement**: Updated to Version 2.0 with improved git operations and error handling
- **Documentation Updates**: Enhanced README with comprehensive workflow documentation
- **Branch Handling**: Improved default branch detection and git operation reliability

The repository demonstrates a complete automated documentation system that continuously maintains README accuracy as the codebase evolves.