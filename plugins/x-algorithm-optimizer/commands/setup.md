---
description: Configure your profile for personalized tweet optimization. Sets your niche, account size, and goals.
---

# X Algorithm Optimizer Setup

Configure your profile to get personalized tweet recommendations.

## What This Does

Creates a config file at `~/.x-algorithm-optimizer.json` with your preferences:
- Content niche (what you tweet about)
- Account size (affects strategy recommendations)
- Goals (what you're optimizing for)

## Setup Flow

Ask the user these questions and save their answers:

### 1. Content Niche

Ask: "What do you primarily tweet about?"

Options:
- Tech/Developer content
- Business/Entrepreneurship
- Fitness/Health
- Finance/Investing
- Creative/Art/Design
- Marketing/Growth
- Education/Learning
- Lifestyle/Personal brand
- Other (let them specify)

### 2. Account Size

Ask: "What's your current follower count?"

Options:
- Small (under 1K followers) - Focus on niche consistency and engagement
- Medium (1K-10K followers) - Balance growth with community building
- Large (10K-100K followers) - Focus on maintaining engagement rate
- Very Large (100K+ followers) - Focus on quality and avoiding negative signals

### 3. Goals (can select multiple)

Ask: "What are your main goals? (select all that apply)"

Options:
- Grow followers
- Increase engagement
- Build authority/credibility
- Drive traffic (to website/product)
- Build community
- Generate leads/sales

### 4. Posting Style Preferences

Ask: "What's your preferred tone?"

Options:
- Professional/Educational
- Casual/Conversational
- Bold/Contrarian
- Inspirational/Motivational
- Humorous/Witty
- Mix of styles

## Save Config

After collecting answers, save to `~/.x-algorithm-optimizer.json`:

```json
{
  "niche": "tech",
  "nicheDescription": "Tech/Developer content",
  "accountSize": "small",
  "followerCount": "under 1K",
  "goals": ["growth", "engagement", "authority"],
  "tone": "mix",
  "setupDate": "2024-01-22",
  "version": "1.0"
}
```

## Confirmation

After saving, confirm:

```
Profile saved to ~/.x-algorithm-optimizer.json

Your settings:
- Niche: Tech/Developer content
- Account: Small (under 1K followers)
- Goals: Grow followers, Increase engagement, Build authority
- Tone: Mix of styles

You can now use /tweet <idea> for personalized recommendations.
To update your profile, run /tweet setup again.
```
