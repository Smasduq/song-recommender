# Song Recommender - Project Details

## Overview

The Song Recommender is an AI agent skill designed to facilitate conversational music recommendations. It provides a structured framework for AI agents to gather user preferences, search for real songs, and deliver personalized recommendations with clear reasoning.

## Purpose

This project aims to create a consistent, ethical, and user-friendly approach to AI-powered song recommendations. It emphasizes:

- **Personalization**: Recommendations based on actual user preferences (mood, taste, context)
- **Transparency**: Each recommendation includes a clear explanation of why it fits
- **Verification**: Songs must be verified to exist before being recommended
- **Ethical practices**: No lyrics reproduction, no piracy assistance, no private data collection
- **Legal guidance**: Points users to legal streaming/purchase options

## Core Functionality

### 1. Preference Collection
The skill guides agents to ask about:
- **Mood/Occasion**: Relaxing, workout, studying, sad, party, road trip, etc.
- **Favorites**: 2-3 artists or songs the user already loves
- **Preferences**: Genres, languages, eras they like
- **Dislikes**: Anything they want to avoid
- **Recipient**: Who the recommendations are for (self or someone else)
- **Optional**: Energy level, explicit content preferences, discovery vs familiarity

### 2. Recommendation Process
1. Collect preferences (or skip if already detailed)
2. Summarize taste in one line to confirm understanding
3. Search for candidate songs using web search
4. Verify each candidate song exists
5. Select 3 songs (mixing safe picks, slightly new picks, and wildcard if discovery desired)
6. Format output with explanations and links
7. Offer next steps

### 3. Output Format
```
Your taste: <one-line summary>

1. "<Song title>" by <Artist>
   Why it fits: <one sentence tied to what the user told you>
   Find it: <link from search results, or search tip>

2. ...
3. ...

Want more like #2, a different mood, or a longer playlist?
```

## Project Structure

```
song_recommender/
├── SKILL.md                    # Main skill definition for AI agents
├── README.md                   # Project overview and usage
├── LICENSE                     # MIT License
├── CONTRIBUTING.md             # Contribution guidelines
├── .gitignore                  # Git ignore rules
└── references/
    └── question_guide.md       # Example question phrasing
```

## Key Constraints & Rules

- **No hallucination**: Don't invent songs, artists, albums, release years, or links
- **No lyrics**: Never reproduce song lyrics, even partial
- **Privacy-focused**: Don't search for or guess private details about real people
- **No piracy**: Don't help download or pirate music; suggest legal options
- **Bounded results**: Recommend maximum of 3 songs unless explicitly requested
- **Concise**: Keep reasons to one sentence each
- **Graceful fallback**: If search unavailable, recommend well-known songs and mark as "from memory"
- **Respectful**: Don't ask for sensitive info (name, address, health, finances)

## Use Cases

- **Quick picks**: "Recommend me a song for the gym"
- **Mood-based**: "Find music for when I'm sad"
- **Context-aware**: "Songs for a road trip with friends"
- **Gift help**: "Recommend songs for someone who likes indie folk"
- **Exploration**: "Something new like artists I already love"

## Target Users

This skill is designed for AI agents to use when helping humans discover music. It's suitable for:
- General-purpose AI assistants
- Music-focused chatbots
- Agent frameworks that support skills/plugins

## License

MIT License - open source and freely usable for both personal and commercial purposes.

## Version

Current state: Open source release (v1.0)
