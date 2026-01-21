# Mert Karadayi's Claude Code Plugins

A monorepo marketplace for Claude Code plugins.

## Installation

Add this marketplace to Claude Code:

```bash
/plugin marketplace add mertkaradayi/claude-plugins
```

## Available Plugins

### X Algorithm Optimizer

Optimize tweets based on X's open-source recommendation algorithm.

**Install:**
```bash
/plugin install x-algorithm-optimizer@mertkaradayi
```

**Usage:**
```bash
/tweet <your idea>           # Generate optimized tweets
/tweet thread: <topic>       # Generate a thread
/tweet analyze: <draft>      # Analyze existing draft
```

**Features:**
- Multiple tweet versions with different hooks
- Algorithm grades (A-F) based on real signals
- SimClusters alignment scoring
- Timing & media recommendations
- Post-tweet action checklists

---

## Repository Structure

```
claude-plugins/
├── .claude-plugin/
│   └── marketplace.json     # Plugin catalog
├── plugins/
│   └── x-algorithm-optimizer/
│       ├── .claude-plugin/
│       │   └── plugin.json
│       ├── commands/
│       │   └── tweet.md
│       ├── skills/
│       │   └── x-algorithm-optimizer/
│       │       └── SKILL.md
│       └── README.md
└── README.md
```

## Adding New Plugins

1. Create a new folder under `plugins/`
2. Add the plugin structure (`.claude-plugin/plugin.json`, commands, skills, etc.)
3. Add an entry to `.claude-plugin/marketplace.json`
4. Push to GitHub

## License

MIT
