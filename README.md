# Claude README Sync

An automated GitHub Actions workflow system for intelligent README synchronization using Claude AI.

## 🎯 Purpose

This repository demonstrates and provides a robust automated workflow that uses Claude AI to analyze weekly code changes and intelligently update documentation. The system performs comprehensive change analysis and generates meaningful README updates based on actual development activity.

## 🤖 How It Works

The automated workflow system operates on a weekly schedule with sophisticated change detection:

### Weekly Analysis Process
- **Scheduled Execution**: Every Monday at 4:30 AM UTC  
- **Change Detection**: Analyzes the last 7 days of commits for meaningful changes
- **Intelligent Updates**: Uses Claude AI (Sonnet 4 model) to understand changes and update documentation accordingly
- **Pull Request Generation**: Creates detailed PRs with analysis summaries when updates are needed

### Workflow Features
- ✅ **Smart Change Analysis**: Generates detailed analysis files including commit history, file changes, and code diffs
- ✅ **Conditional Execution**: Only runs when actual changes are detected (skips empty weeks)
- ✅ **Comprehensive Reporting**: Provides detailed analysis with commit counts, file changes, and line modifications
- ✅ **Automated PR Creation**: Creates pull requests with rich metadata and change summaries
- ✅ **Clean Execution**: Properly manages temporary files and maintains repository cleanliness

## 📋 Workflow Configuration

The main workflow is defined in [`.github/workflows/claude-readme.yml`](.github/workflows/claude-readme.yml) and includes:

### Key Components
- **Change Analysis Engine**: Analyzes repository changes over the past 7 days
- **Claude Integration**: Uses `anthropics/claude-code-base-action@beta` for intelligent documentation updates
- **Data Source Generation**: Creates comprehensive analysis files for Claude processing
- **Automated PR System**: Handles branch creation, commits, and pull request generation

### Configuration Parameters
```yaml
Schedule: '30 13 * * *'  # Monday at 4:30 AM UTC
Model: claude-sonnet-4-20250514
Timeout: 15 minutes
```

## 🔧 Recent Improvements (June 2025)

The system has undergone significant refinements and improvements:

### Workflow Evolution
- **Consolidated Architecture**: Streamlined from multiple workflow files to a single, robust `claude-readme.yml`
- **Enhanced Change Detection**: Improved git diff analysis and commit tracking
- **Better Error Handling**: Robust fallback strategies for edge cases
- **Optimized Performance**: Reduced complexity while maintaining functionality

### Technical Enhancements
- **Proper Git Diff Handling**: Fixed commit range comparisons for accurate change detection
- **Improved File Management**: Better temporary file handling and cleanup
- **Enhanced PR Descriptions**: More detailed and informative pull request descriptions
- **Better Scheduling**: Optimized cron timing for reliable execution

## 🚀 Usage

### Manual Trigger
The workflow can be manually triggered with optional force update:

```bash
# Via GitHub Actions UI or API
# Set 'force_update' to true to run even when no changes are detected
```

### Required Secrets
- `ANTHROPIC_API_KEY`: Your Anthropic API key for Claude access
- `GITHUB_TOKEN`: Automatically provided by GitHub Actions

## 📊 Analysis Output

When changes are detected, the system generates:

1. **Detailed Analysis File**: Complete commit history with files and statistics
2. **Change Diff**: Full git diff showing exact code modifications  
3. **Commit Summary**: Recent commit messages with authors and dates
4. **File Change List**: All modified files in the analysis period

## 🎯 Benefits

- **Automated Documentation**: Keeps README files current with minimal manual intervention
- **Intelligent Analysis**: Claude AI understands context and generates meaningful updates
- **Development Workflow Integration**: Seamlessly integrates with existing development processes
- **Comprehensive Tracking**: Provides detailed analysis of all repository changes

## ⚙️ Technical Details

- **Language**: GitHub Actions YAML with Bash scripting
- **AI Integration**: Anthropic Claude Sonnet 4 model
- **Execution Environment**: Ubuntu latest with full git history
- **Permissions**: Requires `contents: write` and `pull-requests: write`

---

*Last Updated: June 2025 - Automated documentation sync system with 86 commits analyzed and 4 workflow files optimized*