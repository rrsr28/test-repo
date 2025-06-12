# Automated README Synchronization

A GitHub Action-based system for automatically analyzing code changes and keeping README documentation in sync with your codebase.

## Features

- 🔄 Weekly scheduled documentation updates
- 📊 Analyzes commit history to identify relevant changes
- 🤖 Uses Claude AI to intelligently update README content
- 🔍 Focuses only on sections that need updating
- 🔀 Creates pull requests or direct commits based on branch protection settings

## Workflows

### Claude README Sync (Daily)

Runs daily at 2:50 AM UTC to check for recent changes and update documentation accordingly.

### Weekly AI-Powered README Update

Runs every Monday at 2:07 AM UTC to perform a comprehensive analysis of the past week's development activity:

- Analyzes commits from the past 7 days
- Generates detailed change summaries
- Preserves existing README structure and style
- Updates only relevant sections based on actual code changes

## Configuration

The workflows are pre-configured with sensible defaults but can be customized through:

- Workflow files in `.github/workflows/`
- Schedule adjustments via cron expressions
- Optional manual triggers with workflow dispatch

## Usage

This system works automatically once installed. The workflows will:

1. Analyze recent code changes on the main branch
2. Determine if README updates are required
3. Create a new branch for changes if needed
4. Update only the relevant sections of your README
5. Submit changes via pull request or direct commit
6. Provide detailed summary of what was updated

## Requirements

- GitHub repository with Actions enabled
- Anthropic API key stored as repository secret
- Appropriate repository permissions for the workflows

## Last Updated

2025-06-12