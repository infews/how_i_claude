# Communication Patterns Analysis - Data Index

Analysis of 1,352 messages from Jess's Claude Code sessions across 4 projects.

---

## Raw Data Files

### `/tmp/jess_messages_raw.json` (3.8 MB)
All 1,352 human messages extracted from conversation logs.

**Structure:**
```json
{
  "project": "personal-log",
  "session": "df3f5123",
  "timestamp": "2025-12-04T02:07:11.977Z",
  "human": "Hey, something's gone wrong with my mobile app...",
  "assistant_before": null,
  "is_first": true
}
```

**Fields:**
- `project`: Which project folder (personal-log, blog, pl-context, roguelike)
- `session`: Session ID (first 8 chars of conversation filename)
- `timestamp`: When the message was sent
- `human`: The actual message content
- `assistant_before`: Claude's message immediately before (for context)
- `is_first`: Whether this was the first message in the session

---

### `/tmp/jess_messages_analyzed.json` (1.8 MB)
Messages with computed characteristics.

**Additional fields:**
- `word_count`: Number of words
- `char_count`: Number of characters
- `starts_lowercase`: Boolean
- `has_question`: Contains "?"
- `has_ellipsis`: Contains "..."
- `has_code`: Contains backticks
- `references_previous`: References earlier context

---

### `/tmp/jess_conversation_pairs.json` (3.1 MB)
776 message pairs for cause-effect analysis.

**Structure:**
```json
{
  "human": "yup that worked",
  "assistant_response": "Great! Now let's...",
  "human_category": "feedback",
  "response_type": "continuation"
}
```

---

### `/tmp/jess_communication_patterns.json` (10 KB)
Structured analysis of identified patterns.

**Contains:**
- `meta`: Total messages, projects, date range
- `communication_patterns`: 8 patterns with frequencies, signal words, examples
- `style_characteristics`: Lowercase starts, question frequency, ellipsis usage
- `notable_openers`: Most common message starters

---

## Teaching Documents

### `/tmp/agentic_ai_workflow_guide.md`
Main practical guide: "Getting Effective Results with Agentic AI"
- Step 1: Know what you're trying to accomplish
- Step 2: Communicate to stay aligned (detail, validation, feedback)
- Step 3: Recognize when you're stuck
- Step 4: For complex work, use structure

### `/tmp/claude_communication_guide.md`
Comprehensive guide with all 8 patterns, session arc, anti-patterns.

### `/tmp/claude_quick_reference.md`
One-page cheat sheet.

### `/tmp/meta_blog_post.md`
Blog post telling the story of this analysis session.

---

## Projects Analyzed

| Project | Description |
|---------|-------------|
| `personal-log` | Mobile app development (React Native, Expo, Firebase) |
| `blog` | Jekyll blog with syntax highlighting |
| `pl-context` | Related tooling/infrastructure |
| `roguelike` | Game project |

**Date range:** 2025-12-04 to 2026-01-17

---

## Key Statistics

- **Total messages:** 1,352
- **Feedback loop messages:** ~30%
- **Quick questions:** ~16%
- **Thinking aloud:** ~9%
- **Affirmation + pivot:** ~9%
- **Course corrections:** ~8%
- **Starts lowercase:** 52%
- **Contains questions:** 51%
- **Uses ellipsis:** 29%
- **References previous context:** 80%
- **Bare affirmations ("yes", "ok"):** 0.1%

---

## How to Query the Data

```bash
# Count messages by project
cat /tmp/jess_messages_raw.json | python3 -c "
import json, sys
from collections import Counter
data = json.load(sys.stdin)
print(Counter(m['project'] for m in data))
"

# Find messages containing a pattern
cat /tmp/jess_messages_raw.json | python3 -c "
import json, sys
data = json.load(sys.stdin)
for m in data:
    if 'your pattern' in m.get('human', '').lower():
        print(m['human'][:200])
        print('---')
"

# Analyze message lengths
cat /tmp/jess_messages_analyzed.json | python3 -c "
import json, sys
data = json.load(sys.stdin)
lengths = [m['word_count'] for m in data]
print(f'Mean: {sum(lengths)/len(lengths):.1f} words')
print(f'Max: {max(lengths)} words')
"
```
