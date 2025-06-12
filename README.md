# test-repo

A GitHub repository with automated weekly README maintenance powered by Claude AI.

## 🤖 Automated Documentation System

This repository features a sophisticated automated documentation workflow that analyzes code changes and maintains up-to-date README documentation.

### ⏰ Weekly README Updates

- **Schedule**: Runs every Monday at 11:21 AM UTC via GitHub Actions
- **Analysis Period**: Reviews the last 7 days of development activity  
- **AI-Powered**: Uses Claude Sonnet 4 to analyze changes and update documentation
- **Smart Updates**: Only creates pull requests when meaningful changes are detected

### 📊 How It Works

The automated system (`claude-readme.yml`) performs comprehensive analysis:

1. **Change Detection**: Analyzes commits, file changes, and code modifications from the past week
2. **Data Collection**: Generates detailed analysis files with commit history, diffs, and statistics
3. **AI Analysis**: Claude AI processes the changes and updates documentation accordingly
4. **PR Creation**: Automatically creates pull requests with detailed change summaries
5. **Clean Operations**: Removes temporary analysis files after processing

### 🔧 Workflow Features

- **Timeout Protection**: 30-minute workflow timeout with 15-minute Claude processing limit
- **Detailed Analysis**: Tracks additions/deletions, file changes, and commit statistics  
- **Smart Branching**: Creates timestamped branches for documentation updates
- **Cross-Referencing**: Links documentation changes back to triggering code modifications
- **Fallback Handling**: Graceful handling of edge cases and repository states

## Repository Structure

```
.github/workflows/
├── claude-readme.yml    # Weekly automated README maintenance workflow
README.md               # This file - automatically maintained weekly
```

## Development

This repository demonstrates automated documentation maintenance. The README is updated weekly based on actual code changes, ensuring documentation stays current with development activities.

## Configuration

The automation requires:
- `ANTHROPIC_API_KEY` secret for Claude AI integration
- Standard GitHub Actions permissions for repository operations

---
*Last updated: 2025-06-12 via automated weekly analysis*