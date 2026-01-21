# Mert Karadayi's Claude Code Plugins

Curated Claude Code plugins for productivity and social media optimization.

## Installation

Add this marketplace to Claude Code:

```bash
/plugin marketplace add mertkaradayi/claude-plugins
```

## Available Plugins

### X Algorithm Optimizer

**Description:** Optimize tweets based on X's open-source recommendation algorithm. Generates algorithm-graded tweet versions with timing, media, and engagement strategies.

**Install:**
```bash
/plugin install x-algorithm-optimizer@mertkaradayi
```

**What you get:**
- `/tweet <idea>` - Generate optimized tweet versions
- `/tweet thread: <topic>` - Generate optimized threads
- `/tweet analyze: <draft>` - Analyze existing drafts
- Algorithm grades (A-F) based on real signals
- SimClusters alignment scoring
- Timing & media recommendations
- Post-tweet action checklists

**Repository:** https://github.com/mertkaradayi/x-algorithm-optimizer

---

## How It Was Built

I used Claude Code to analyze X's open-source recommendation algorithm (50,000+ lines across Scala, Java, and Python), then distilled the insights into the x-algorithm-optimizer plugin.

Key algorithm components analyzed:
- **SimClusters**: 145K topic communities
- **RealGraph**: User relationship scoring
- **Heavy Ranker**: 15 engagement predictions
- **UTEG**: Network amplification

## License

MIT
