# Test Repository - Automated README Updates

This repository serves as a test environment for automated README maintenance using Claude Code and GitHub Actions.

## Overview

This project demonstrates an automated workflow that:
- Analyzes weekly code changes
- Updates documentation automatically
- Creates pull requests with detailed change summaries
- Maintains accurate, up-to-date project documentation

## Workflow Features

### 🤖 Automated Analysis
- **Schedule**: Every Monday at 4:30 AM UTC (configurable)
- **Manual Trigger**: Supports workflow dispatch with force update option
- **Change Detection**: Analyzes the last 7 days of commits automatically

### 📊 Comprehensive Reporting
- Commit analysis with author and date information
- File change tracking and statistics
- Line-by-line diff generation
- Automated pull request creation with detailed summaries

### 🛡️ Security & Reliability
- Proper permissions management (contents: write, pull-requests: write)
- Timeout protection (30-minute limit)
- Automatic cleanup of temporary files
- Smart skipping when no changes are detected

## Configuration

The workflow uses GitHub Actions with the following key components:
- **Claude Model**: `claude-sonnet-4-20250514`
- **Timeout**: 15 minutes for README updates
- **Permissions**: Limited tool access for security
- **Branch Naming**: `readme-update-{timestamp}` format

## Usage

1. **Automatic**: The workflow runs weekly on schedule
2. **Manual**: Trigger via workflow dispatch in GitHub Actions
3. **Force Update**: Use the force_update input to run even without changes

## Last Updated

*Generated: 2025-06-28*

---
*This README is automatically maintained by Claude Code. Changes are analyzed weekly and documentation is updated accordingly.*