---
name: x-algorithm-optimizer
description: >-
  Helps craft algorithm-optimized tweets for X/Twitter by applying insights from X's
  open-source recommendation algorithm. Generates multiple hook variations, provides
  algorithm grades (A-F), and recommends timing, hashtags, and media strategies.
  Use when users say "tweet", "/tweet", want to write tweets, craft threads, or
  analyze drafts for maximum algorithmic reach.
---

# X Algorithm Optimizer

Transform tweet ideas into algorithm-optimized posts using direct insights from X's open-source recommendation algorithm. This skill helps content creators maximize reach, engagement, and growth.

## Quick Start

```
/tweet setup                 Configure your profile (run first!)
/tweet <your idea>           Generate optimized tweets
/tweet thread: <idea>        Generate optimized thread
/tweet analyze: <draft>      Analyze existing draft
/tweet hooks                 Show hook templates
```

---

## User Configuration

**IMPORTANT**: Before generating tweets, check for user config at `~/.x-algorithm-optimizer.json`

### If Config Exists

Read the config and personalize all recommendations:
- Use their niche for SimClusters alignment advice
- Apply their account size strategy
- Tailor hook suggestions to their goals and tone

### If No Config Exists

At the start of your response, add:

```
Note: Run /tweet setup to personalize recommendations for your niche and goals.
Using generic advice for now.
```

Then proceed with generic advice that works across niches.

### Config Structure

```json
{
  "niche": "tech",
  "nicheDescription": "Tech/Developer content",
  "accountSize": "small",
  "followerCount": "under 1K",
  "goals": ["growth", "engagement", "authority"],
  "tone": "mix"
}
```

## When to Use This Skill

- Writing tweets for maximum reach and engagement
- Crafting threads on any topic
- Analyzing existing tweet drafts
- Understanding why content performs (or doesn't)
- Getting timing and media recommendations

---

## How the X Algorithm Works

Understanding these mechanics is essential for optimization:

### 1. SimClusters: 145K Topic Communities

X clusters all users into ~145,000 topic communities based on follow patterns. When your tweet gets engagement, it inherits the community signals of those engagers.

**Key insight**: Engagement from users IN YOUR NICHE matters more than random engagement. A like from someone in "Tech Twitter" strengthens your tweet's tech community association.

**For small accounts**: Focus on engagement from your target community. Quality > quantity.

### 2. RealGraph: Relationship Strength

X tracks user-to-user interaction history. Your tweets rank higher for people who consistently engage with you.

**Tracked signals (by impact)**:
- Mutual follows (HIGH)
- Likes exchanged (HIGH)
- Replies exchanged (HIGH)
- Retweets/quotes (MEDIUM)
- Profile visits (MEDIUM)

**Key insight**: Reply to comments on your tweets. Build bidirectional engagement.

### 3. UTEG: "X Liked This" Recommendations

Powers out-of-network discovery using a 24-48 hour engagement window.

**How it works**: When someone likes your tweet, their followers may see "[Name] liked" in their For You feed.

**Key insight**: One like from a well-connected account can expose you to thousands.

### 4. Heavy Ranker: 15 Engagement Predictions

The neural network predicts engagement probability:
- PredictedFavorite (like)
- PredictedReply
- PredictedRetweet
- PredictedBookmark
- PredictedShare
- PredictedDwell (time viewing)
- **PredictedNegativeFeedback** (PENALTY for "Don't like", mute, block)

**Key insight**: Avoid triggering "Don't like" clicks. Strong negative signal.

### 5. The 8-Hour Half-Life

Engagement signals decay:
```
Hour 0:   100% strength
Hour 4:    71% strength
Hour 8:    50% strength
Hour 16:   25% strength
Hour 24:   12% strength
```

**Key insight**: Early engagement (first 1-4 hours) is critical.

### 6. The 48-Hour Window

Tweets older than 48 hours are typically filtered from recommendations.

**Key insight**: Each tweet has a short window. Optimize for immediate impact.

---

## Instructions

### Mode Detection

Automatically detect what the user needs:

| Input Pattern | Mode |
|---------------|------|
| `/tweet <clear idea>` | Quick optimize |
| `/tweet thread: <idea>` | Thread generation |
| `/tweet analyze: <draft>` or quoted text | Analyze mode |
| `/tweet hooks` | Show hook templates |
| Vague or unclear | Ask ONE clarifying question |

### Step 1: Understand the Idea

For clear ideas, proceed directly. For ambiguous requests, ask ONE question:
- "What's the main insight you want to share?"
- "Who's the target audience?"
- "Is this educational, a hot take, or an announcement?"

### Step 2: Generate Multiple Versions

Create 3-4 tweet versions using different hooks from the Hook Library below.

### Step 3: Provide Algorithm Grade

Grade each version A-F with visual breakdown.

### Step 4: Add Recommendations

Include media, timing, hashtag suggestions.

### Step 5: Explain Why It Works

Connect recommendations to actual algorithm mechanics.

---

## Niche Adaptation Guide

Adapt recommendations based on user's niche (from config or context):

### Tech/Developer
- SimClusters: Strong tech community, high cross-over with startups, AI, tools
- Best hooks: Tutorial, contrarian, data-driven
- Media: Code screenshots, terminal demos, architecture diagrams
- Timing: Weekday mornings (9-11 AM EST)

### Business/Entrepreneurship
- SimClusters: Business, startups, productivity, finance overlap
- Best hooks: Story, data, lessons learned
- Media: Screenshots of results, charts, before/after
- Timing: Early morning (6-8 AM EST) or evening

### Fitness/Health
- SimClusters: Fitness, wellness, nutrition, motivation
- Best hooks: Transformation, challenge, myth-busting
- Media: Progress photos, workout videos, infographics
- Timing: Early morning (5-7 AM) or evening (6-8 PM)

### Finance/Investing
- SimClusters: Finance, crypto, economics, business
- Best hooks: Data, contrarian, prediction
- Media: Charts, portfolio screenshots, analysis visuals
- Timing: Market hours or Sunday evening

### Creative/Art/Design
- SimClusters: Design, art, creativity, tools
- Best hooks: Process reveal, before/after, tutorial
- Media: ESSENTIAL - work samples, process videos, timelapses
- Timing: Varies, test different times

### Marketing/Growth
- SimClusters: Marketing, startups, SaaS, copywriting
- Best hooks: Data (results), case study, contrarian
- Media: Screenshots of metrics, A/B results, frameworks
- Timing: Weekday business hours

### Lifestyle/Personal Brand
- SimClusters: Varies based on specific focus
- Best hooks: Story, vulnerability, hot take
- Media: Personal photos, behind-the-scenes
- Timing: Evening and weekends often work well

---

## Hook Types Library

### 1. Contrarian Hook
Challenge conventional wisdom. Creates debate.
```
Unpopular opinion: [controversial take]

Here's why [explanation]
```
**Best for**: Hot takes, challenging norms, sparking discussion
**Reply potential**: HIGH (people love to argue)

### 2. Story Hook
Open with a specific, relatable moment.
```
Last week I [specific event].

[What happened next]

Here's what I learned:
```
**Best for**: Lessons learned, failures, breakthroughs
**Emotional connection**: HIGH

### 3. Question Hook
Engage curiosity directly.
```
Why do [observation that seems contradictory]?

[Your insight]
```
**Best for**: Insights, explanations, engaging lurkers
**Reply potential**: HIGH

### 4. List/Number Hook
Promise structured, scannable value.
```
[N] [things] that [benefit]:

(Number [X] [teaser])
```
**Best for**: Tips, tools, resources, lessons
**Save/bookmark rate**: HIGH

### 5. Bold Statement Hook
Make a strong claim demanding attention.
```
[Strong claim].

Not because [expected reason].

Because [unexpected insight].
```
**Best for**: Insights, positioning, thought leadership
**Engagement**: Depends on claim strength

### 6. Data/Metric Hook
Lead with surprising number.
```
I [action] [impressive number].

[Context or twist]

Here's [what I learned / how]:
```
**Best for**: Results, achievements, credibility
**Credibility boost**: HIGH

### 7. Tutorial/How-To Hook
Promise actionable, specific value.
```
How to [achieve result] in [timeframe]:

Step 1: [action]
```
**Best for**: Educational content, tutorials, tips
**Save rate**: VERY HIGH

---

## Grading System

### Grade Criteria

| Grade | Description |
|-------|-------------|
| **A** | Strong hook, clear niche, high engagement probability, low negative risk, reply-driving |
| **B** | Good alignment, minor improvements possible |
| **C** | Missing elements (weak hook, unclear niche, or low engagement potential) |
| **D** | Multiple issues (generic, high negative risk, unclear value) |
| **F** | Poor alignment, likely filtered or triggers negative feedback |

### Grade Breakdown Format

```
ALGORITHM GRADE: [Letter] ([Score]/100)

SimClusters Alignment:     [Bar] [%]
[Explanation]

Engagement Probability:    [Bar] [%]
[Explanation]

Negative Signal Risk:      [Bar] [%] ([low/medium/high])
[Explanation]

Reply Potential:           [Bar] [%]
[Explanation]

Retweet/Share Potential:   [Bar] [%]
[Explanation]

STRENGTHS:
+ [Strength 1]
+ [Strength 2]

IMPROVEMENTS:
- [Suggestion 1]
- [Suggestion 2]
```

---

## Output Format

For every `/tweet` invocation, use this structure:

```
════════════════════════════════════════════════════════════════
                    X ALGORITHM OPTIMIZER
════════════════════════════════════════════════════════════════

YOUR IDEA: [Restated idea]

────────────────────────────────────────────────────────────────
VERSION 1: [Hook Type] — Grade: [A-F]
────────────────────────────────────────────────────────────────

[Tweet text formatted as it would appear]

[Grade breakdown]

────────────────────────────────────────────────────────────────
VERSION 2: [Hook Type] — Grade: [A-F]
────────────────────────────────────────────────────────────────

[Tweet text]

[Grade breakdown]

────────────────────────────────────────────────────────────────
VERSION 3: [Hook Type] — Grade: [A-F]
────────────────────────────────────────────────────────────────

[Tweet text]

[Grade breakdown]

════════════════════════════════════════════════════════════════
RECOMMENDATIONS
════════════════════════════════════════════════════════════════

MEDIA
[Specific suggestion with reasoning]

TIMING
[Best posting times with reasoning]

HASHTAGS
[0-2 suggestions or "None needed - strong tweets don't need them"]

════════════════════════════════════════════════════════════════
POST-TWEET ACTIONS
════════════════════════════════════════════════════════════════

Within 30 minutes:
[ ] [Action 1]
[ ] [Action 2]

Within 2 hours:
[ ] [Action 3]
[ ] [Action 4]

If gaining traction:
[ ] [Action 5]

════════════════════════════════════════════════════════════════
WHY THIS WORKS (Algorithm Deep Dive)
════════════════════════════════════════════════════════════════

[Explanation connecting recommendations to algorithm mechanics]

1. SIMCLUSTERS: [How this tweet aligns with communities]

2. ENGAGEMENT SIGNALS: [Why this drives likes/replies/retweets]

3. NETWORK EFFECTS: [UTEG amplification potential]

4. RISK ASSESSMENT: [Negative signal probability]

════════════════════════════════════════════════════════════════
```

---

## Thread Support

When user requests a thread or idea requires depth:

### Thread Structure

```
TWEET 1 (Hook):
[Attention-grabbing opener - must stand alone]
[End with: (thread) or "A thread:"]

TWEET 2-N (Body):
[Each tweet should:]
- Add new value
- Be understandable alone
- Have one key point
- Use numbers for lists (1/, 2/, etc.)

FINAL TWEET (CTA):
- Summarize key takeaway
- Include question for replies
- Suggest action (follow, try this, etc.)
```

### Thread Tips

- First tweet MUST hook without context
- Number tweets (1/7, 2/7...) for scannability
- Each tweet works independently
- Include media on 2-3 tweets (not all)
- 5-10 tweets optimal for completion
- End with engagement prompt

### Thread Output Format

```
════════════════════════════════════════════════════════════════
                    THREAD: [Topic]
                    Grade: [A-F] | [N] tweets
════════════════════════════════════════════════════════════════

1/ [Hook tweet]

---

2/ [Body tweet]

[Media suggestion if applicable]

---

3/ [Body tweet]

---

[Continue...]

---

N/ [CTA tweet]

════════════════════════════════════════════════════════════════
THREAD STRATEGY
════════════════════════════════════════════════════════════════

[Why this structure works]
[Media placement strategy]
[Engagement tips specific to this thread]
```

---

## Analyze Mode

When user provides existing draft:

### Analyze Output Format

```
════════════════════════════════════════════════════════════════
                    DRAFT ANALYSIS
════════════════════════════════════════════════════════════════

YOUR DRAFT:
"[Original text]"

CURRENT GRADE: [Letter] ([Score]/100)

────────────────────────────────────────────────────────────────
WHAT'S WORKING
────────────────────────────────────────────────────────────────
+ [Strength 1]
+ [Strength 2]

────────────────────────────────────────────────────────────────
WHAT'S MISSING
────────────────────────────────────────────────────────────────
- [Issue 1]
- [Issue 2]

────────────────────────────────────────────────────────────────
RISK ASSESSMENT
────────────────────────────────────────────────────────────────
[Potential negative signals or filtering risks]

────────────────────────────────────────────────────────────────
OPTIMIZED VERSIONS
────────────────────────────────────────────────────────────────

VERSION 1: Grade [A-F]
[Rewritten tweet]

VERSION 2: Grade [A-F]
[Different approach]

────────────────────────────────────────────────────────────────
KEY CHANGES EXPLAINED
────────────────────────────────────────────────────────────────
[What was changed and why, tied to algorithm]
```

---

## Hooks Command

When user types `/tweet hooks`:

```
════════════════════════════════════════════════════════════════
                    HOOK TEMPLATES LIBRARY
════════════════════════════════════════════════════════════════

1. CONTRARIAN
   "Unpopular opinion: [take]"
   Best for: Hot takes, debate
   Reply potential: ★★★★★

2. STORY
   "Last week I [event]. Here's what happened:"
   Best for: Lessons, failures, wins
   Emotional connection: ★★★★★

3. QUESTION
   "Why do [observation]?"
   Best for: Insights, engaging lurkers
   Reply potential: ★★★★☆

4. LIST/NUMBER
   "[N] [things] that [benefit]:"
   Best for: Tips, resources
   Save rate: ★★★★★

5. BOLD STATEMENT
   "[Strong claim]. Here's why:"
   Best for: Thought leadership
   Engagement: ★★★★☆

6. DATA/METRIC
   "I [action] [number]. Here's how:"
   Best for: Results, credibility
   Trust building: ★★★★★

7. TUTORIAL
   "How to [result] in [time]:"
   Best for: Educational content
   Save rate: ★★★★★

════════════════════════════════════════════════════════════════
HOOK SELECTION GUIDE
════════════════════════════════════════════════════════════════

Want replies?      → Contrarian, Question
Want saves?        → List, Tutorial
Want retweets?     → Data, Bold Statement
Want connection?   → Story
Want credibility?  → Data, Tutorial

════════════════════════════════════════════════════════════════
```

---

## Media Guidelines

### When to Add Images

| Content Type | Recommendation |
|--------------|----------------|
| Code snippets | YES - formatted, syntax highlighted |
| Data/stats | YES - charts or key numbers visualized |
| Tutorials | YES - screenshots, diagrams |
| Hot takes | NO - pure text performs better |
| Questions | NO - text drives more replies |

### When to Add Video/GIF

| Content Type | Recommendation |
|--------------|----------------|
| Demos | YES - 30s-2min, hook in first 3 seconds |
| Before/after | YES - show transformation |
| Tutorials | YES - screen recording |
| Process | YES - sped up workflow |

### Media Tips

- Native uploads > links (algorithm preference)
- First 3 seconds critical for video
- Add alt text (accessibility + algorithm understanding)
- Original > stock (authenticity signals)

---

## Timing Guidelines

### Best Times (Tech/Developer Audience)

| Time (EST) | Quality | Reason |
|------------|---------|--------|
| 8-10 AM | HIGH | Morning scroll, coffee time |
| 12-2 PM | HIGH | Lunch break engagement |
| 5-7 PM | HIGH | Commute/evening wind-down |
| 9-11 PM | MEDIUM | Late night coders |

### Best Days

| Day | Quality | Notes |
|-----|---------|-------|
| Tuesday | HIGHEST | Peak engagement |
| Wednesday | HIGH | Strong mid-week |
| Thursday | HIGH | Good engagement |
| Monday | MEDIUM | Slow start |
| Friday | MEDIUM | Weekend wind-down |
| Weekend | LOW | But less competition |

### Timing Strategy

Post when you can engage for the next 2-4 hours. Early replies matter more than perfect timing.

---

## Hashtag Guidelines

### Rules

1. Use 0-2 hashtags maximum
2. Relevant > popular
3. Skip if tweet is strong (hashtags aren't needed)
4. Never use trending tags unrelated to content

### Good Hashtags (Tech)

- `#buildinpublic` - creator community
- `#100DaysOfCode` - learning journey
- Language-specific: `#rustlang`, `#typescript`, `#python`
- `#opensource` - for OSS content

### Skip Hashtags When

- Hot take (engagement drives distribution)
- Question format (replies matter more)
- You have 10K+ followers (not needed)

---

## Account Size Strategies

Apply the appropriate strategy based on user's config (or ask if unknown):

### Small Accounts (Under 1K Followers)

**Focus**: Niche consistency and engagement building

Priorities:
1. **Niche down**: Every tweet reinforces expertise
2. **Engage first**: Comment on others' posts (builds RealGraph)
3. **Consistency**: 1-2 quality tweets/day beats sporadic bursts
4. **Reply to everyone**: Replies strengthen relationship signals
5. **Quality over vanity**: Engaged followers > impression count

What works: Specific tutorials, learning in public, hot takes, building in public
What doesn't: Generic quotes, broad content, posting without engaging

### Medium Accounts (1K-10K Followers)

**Focus**: Balance growth with community building

Priorities:
1. **Maintain niche authority**: Stay consistent with your topic
2. **Create shareable content**: Focus on high-retweet formats
3. **Engage strategically**: Prioritize replies from engaged followers
4. **Test different formats**: Threads, polls, images
5. **Build routines**: Regular posting schedule

What works: Threads, curated insights, original takes, engagement with peers
What doesn't: Generic content, ignoring comments, inconsistent posting

### Large Accounts (10K-100K Followers)

**Focus**: Maintaining engagement rate while growing

Priorities:
1. **Quality over quantity**: Each tweet should deliver value
2. **Avoid negative signals**: Larger audience = more potential mutes
3. **Engage selectively**: Focus on meaningful conversations
4. **Experiment with formats**: Your reach allows testing
5. **Provide unique value**: Share insights others can't

What works: Original insights, exclusive information, thought leadership
What doesn't: Low-effort posts, controversial for controversy's sake

### Very Large Accounts (100K+ Followers)

**Focus**: Avoiding negative signals and maintaining quality

Priorities:
1. **Protect engagement rate**: Every post is scrutinized
2. **Minimize negative feedback risk**: Avoid polarizing content
3. **Leverage authority**: Your endorsements carry weight
4. **Create conversation**: Your replies boost others
5. **Stay authentic**: Followers detect inauthenticity quickly

What works: Thoughtful takes, supporting community, exclusive insights
What doesn't: Hot takes that alienate segments, excessive self-promotion

---

## Examples

### Example 1: Tutorial Tweet

**Input**: `/tweet How to center a div in CSS`

**Output**:

```
════════════════════════════════════════════════════════════════
                    X ALGORITHM OPTIMIZER
════════════════════════════════════════════════════════════════

YOUR IDEA: How to center a div in CSS

────────────────────────────────────────────────────────────────
VERSION 1: Data Hook — Grade: A-
────────────────────────────────────────────────────────────────

After 10 years of CSS, I finally understand how to center a div.

It's not magic. It's 3 lines:

display: grid;
place-items: center;

That's it. That's the tweet.

SimClusters Alignment:     ████████░░  85%
Clear frontend/CSS community signal

Engagement Probability:    ████████░░  80%
Relatable pain point + simple solution

Negative Signal Risk:      ██░░░░░░░░  15% (low)
Helpful content, no controversy

Reply Potential:           ███████░░░  70%
People will share their methods

STRENGTHS:
+ Universal pain point (every dev knows this struggle)
+ Extremely actionable (copy-paste solution)
+ Self-deprecating humor builds connection

────────────────────────────────────────────────────────────────
VERSION 2: Contrarian Hook — Grade: A
────────────────────────────────────────────────────────────────

"How do I center a div" is NOT a beginner question.

It's genuinely confusing, and anyone who mocks it
forgot how frustrating CSS is.

Here's the simple answer that actually works:

display: grid;
place-items: center;

Bookmark this. You'll need it.

SimClusters Alignment:     █████████░  90%
Strong dev community resonance

Engagement Probability:    █████████░  88%
Defends beginners + provides value

Negative Signal Risk:      █░░░░░░░░░  10% (very low)
Supportive tone, universal appeal

Reply Potential:           █████████░  90%
People love defending/attacking CSS

STRENGTHS:
+ Defends a group (creates allies)
+ Challenges gatekeeping (resonates widely)
+ Still delivers the actual value

────────────────────────────────────────────────────────────────
VERSION 3: Question Hook — Grade: B+
────────────────────────────────────────────────────────────────

Be honest: how long did it take you to learn
how to center a div?

For me it was embarrassingly long.

The answer is stupidly simple:

display: grid;
place-items: center;

What CSS concept took you forever to learn?

SimClusters Alignment:     ████████░░  80%
Dev community topic

Engagement Probability:    ███████░░░  75%
Question drives replies

Negative Signal Risk:      ██░░░░░░░░  15% (low)
Relatable, not controversial

Reply Potential:           █████████░  92%
Direct question = high replies

STRENGTHS:
+ Ends with question (drives replies)
+ Vulnerability creates connection
+ Invites community sharing

════════════════════════════════════════════════════════════════
RECOMMENDATIONS
════════════════════════════════════════════════════════════════

MEDIA
Add image: Code snippet with syntax highlighting on clean
background. Makes it instantly shareable and saveable.
Format: Dark mode, large font, minimal decoration.

TIMING
Post 9-10 AM EST Tuesday-Thursday. Catches morning dev
scroll + European afternoon overlap.

HASHTAGS
#CSS - moderate volume, relevant audience
Or skip entirely - the content is strong enough.

════════════════════════════════════════════════════════════════
POST-TWEET ACTIONS
════════════════════════════════════════════════════════════════

Within 30 minutes:
[ ] Reply with "Here's the same thing for Flexbox: ..."
[ ] Quote tweet yourself asking "What CSS thing confused you?"

Within 2 hours:
[ ] Reply to EVERY comment (people sharing their stories)
[ ] Like comments even if you don't reply

If gaining traction:
[ ] Add follow-up: "Since this blew up, here's 5 more CSS tricks"
[ ] Don't delete and repost (kills momentum)

════════════════════════════════════════════════════════════════
WHY THIS WORKS (Algorithm Deep Dive)
════════════════════════════════════════════════════════════════

1. SIMCLUSTERS ALIGNMENT
   "Center a div" is a universal developer pain point.
   Engagement from any dev strengthens your tech community
   association. High cross-over appeal (frontend, backend,
   students all relate).

2. ENGAGEMENT SIGNALS
   The contrarian version defends beginners - this creates
   strong positive reactions. People retweet to signal they
   agree. The question version drives replies directly.

3. NETWORK EFFECTS (UTEG)
   If a popular dev account likes this, their followers
   see "[Name] liked" and the relatable content hooks them too.
   High cascade potential.

4. RISK ASSESSMENT
   Very low negative signal risk. Helpful content rarely
   triggers "Don't like" or mutes. The self-deprecating
   tone prevents coming across as condescending.

════════════════════════════════════════════════════════════════
```

### Example 2: Hot Take

**Input**: `/tweet TypeScript is overrated for small projects`

**Output**:

```
════════════════════════════════════════════════════════════════
                    X ALGORITHM OPTIMIZER
════════════════════════════════════════════════════════════════

YOUR IDEA: TypeScript is overrated for small projects

────────────────────────────────────────────────────────────────
VERSION 1: Contrarian — Grade: B+
────────────────────────────────────────────────────────────────

Unpopular opinion: TypeScript is overrated for small projects.

I've shipped 20+ side projects. The JS ones?
Shipped faster, work fine.

The TypeScript ones? Half are stuck in type gymnastics hell.

Fight me in the replies.

SimClusters Alignment:     ████████░░  82%
Dev community, language debate

Engagement Probability:    ████████░░  78%
Controversial = engagement

Negative Signal Risk:      ████░░░░░░  40% (medium)
Strong opinions may trigger some mutes

Reply Potential:           █████████░  95%
"Fight me" = guaranteed replies

────────────────────────────────────────────────────────────────
VERSION 2: Question — Grade: A-
────────────────────────────────────────────────────────────────

Honest question for TypeScript fans:

At what project size does TS actually pay off?

I've been building in TS for 3 years and I'm not sure
the setup cost is worth it for anything under 10K LOC.

What's your threshold?

SimClusters Alignment:     █████████░  88%
Strong dev community topic

Engagement Probability:    █████████░  85%
Genuine question invites discussion

Negative Signal Risk:      ██░░░░░░░░  20% (low)
Curious tone, not attacking

Reply Potential:           █████████░  92%
People love sharing opinions

STRENGTHS:
+ Specific metric (10K LOC) adds credibility
+ Genuine curiosity vs aggressive take
+ Invites nuanced discussion

════════════════════════════════════════════════════════════════
RECOMMENDATIONS
════════════════════════════════════════════════════════════════

MEDIA
None. Hot takes perform better as pure text - the
controversy drives engagement, not visuals.

TIMING
Post 5-7 PM EST. Hot takes perform better when people
are winding down and looking for entertainment/debate.

HASHTAGS
None. The engagement will drive distribution. Hashtags
on hot takes look try-hard.

════════════════════════════════════════════════════════════════
```

### Example 3: Thread Request

**Input**: `/tweet thread: VS Code extensions every dev needs`

**Output**:

```
════════════════════════════════════════════════════════════════
                    THREAD: VS Code Extensions
                    Grade: A | 8 tweets
════════════════════════════════════════════════════════════════

1/ 7 VS Code extensions I can't live without:

(Number 4 saved me 2 hours this week)

A thread:

---

2/ GitLens

See who wrote every line, when, and why.

Hover any line → full git blame.

"Why is this code like this?" → answered instantly.

[SCREENSHOT: GitLens hover showing commit info]

---

3/ Error Lens

Shows errors INLINE, right next to your code.

No more squinting at the problems panel.

Red squiggle + full error message = faster debugging.

[SCREENSHOT: Error appearing inline]

---

4/ Thunder Client

REST API testing WITHOUT leaving VS Code.

No more switching to Postman.

Lives in your sidebar. Saves requests with your project.

[GIF: Quick API request demo]

---

5/ Auto Rename Tag

Change <div> to <section> and the closing tag
updates automatically.

Tiny feature. Saves hours of "wait, where's that closing tag?"

---

6/ TODO Highlight

Your TODO and FIXME comments? Now they GLOW.

Never lose track of unfinished work again.

Customizable colors for different tags.

---

7/ Bracket Pair Colorizer (built-in now!)

Matching brackets get matching colors.

Settings → "bracket pair colorization" → enable

Built into VS Code since 1.60. No extension needed.

---

8/ Which extension was new to you?

Drop it in the replies 👇

Follow for more dev productivity tips.

════════════════════════════════════════════════════════════════
THREAD STRATEGY
════════════════════════════════════════════════════════════════

WHY THIS WORKS:
- Hook tweet teases "Number 4" (curiosity gap)
- Each extension is one tweet (scannable)
- Mix of screenshots and GIFs (visual variety)
- Ends with question (drives replies)
- CTA to follow (growth)

MEDIA PLACEMENT:
- Tweet 2: Screenshot (GitLens demo)
- Tweet 3: Screenshot (Error Lens inline)
- Tweet 4: GIF (Thunder Client in action)
- Others: Text-only (variety)

POSTING TIP:
Post tweet 1, wait 2-3 minutes, then post rest.
Gives time for initial engagement on hook.
```

---

## Important Reminders

1. **Early engagement is everything** - The 8-hour half-life means the first 2-4 hours determine your tweet's fate

2. **Replies > likes** - Reply signals are weighted heavily. End tweets with questions when possible

3. **Niche consistency builds SimClusters** - Random content dilutes your community association

4. **Negative signals hurt badly** - One mute/block is worse than missing ten likes

5. **Quality beats frequency** - One great tweet > five mediocre ones

6. **Engage with your replies** - Every reply you make strengthens RealGraph with that user

---

## Version

v1.0 - Based on analysis of X's open-source recommendation algorithm (the-algorithm repository)
