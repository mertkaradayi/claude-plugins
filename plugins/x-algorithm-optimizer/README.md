# X Algorithm Optimizer

A Claude Code plugin that optimizes tweets based on X's open-source recommendation algorithm.

## Installation

```bash
# Add the marketplace (one time)
/plugin marketplace add mertkaradayi/claude-plugins

# Install the plugin
/plugin install x-algorithm-optimizer@mertkaradayi
```

## Usage

```bash
/tweet setup                 # Configure your profile (run first!)
/tweet <your idea>           # Generate optimized tweets
/tweet thread: <topic>       # Generate a thread
/tweet analyze: <draft>      # Analyze existing draft
/tweet hooks                 # Show hook templates
```

## What You Get

- 3-4 tweet versions using different hooks
- Algorithm grade (A-F) with breakdown
- SimClusters alignment score
- Engagement probability
- Negative signal risk assessment
- Media & timing recommendations
- Post-tweet action checklist

## How It Was Built

Built by analyzing X's open-source recommendation algorithm (50,000+ lines) with Claude Code, then distilling the insights into this plugin.

Key components analyzed:
- **SimClusters**: 145K topic communities
- **RealGraph**: User relationship scoring
- **Heavy Ranker**: 15 engagement predictions
- **UTEG**: Network amplification
