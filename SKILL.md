---
name: song-recommender
description: Asks a person a few short questions about their music taste, mood, and situation, then searches for real songs and recommends three that fit them, each with a one-line reason. Use when the user says things like recommend me a song, what should I listen to, or find music for my mood, or asks for songs for a workout, trip, study session, or gift playlist. Not for looking up personal details about real people online, not for reproducing song lyrics, and not for downloading or pirating music.
license: MIT
---

# Song Recommender

Helps an AI agent recommend songs that fit one specific person. The agent
asks the user about their taste, searches for real songs, and explains why
each pick fits.

## When to use

Use this skill when the user wants a song or a short list of songs, for
themselves or for someone they know. Typical requests:

- "Recommend me a song"
- "What should I listen to?"
- "Find music for my mood"
- "I need songs for the gym" or "songs for a road trip"

Do not use it for lyrics, chord sheets, music theory homework, or
downloading music.

## What to gather first

Ask the user directly. Never look the person up online. Ask all questions
in one short message, and skip any the user already answered.

1. Mood or occasion (relaxing, workout, studying, sad, party, road trip)
2. Two or three artists or songs they already love
3. Genres, languages, or eras they like, and anything they dislike
4. Who the songs are for (themselves, or someone else)

If the songs are for someone else, ask the user to describe that person's
taste. Do not search for that person.

Optional extras, only if useful: energy level (calm to intense), whether
clean or explicit lyrics matter, and whether they want familiar or new
music. See `references/question-guide.md` for wording ideas.

If the user does not want to answer, give 3 recommendations anyway from
the little they said, and say what you assumed.

## Process

1. **Collect** the answers above. If the request is already detailed,
   skip straight to step 2.
2. **Summarize** the person's taste in one line to confirm you understood
   (for example "You like calm Afrobeats for late-night studying").
3. **Search** for candidates using web search if available. Search by
   mood, genre, and similar artists, for example "calm Afrobeats study
   songs" or "artists similar to Burna Boy".
4. **Verify** each candidate. Confirm the title and artist exist, using a
   search result. Do not trust memory alone for obscure songs.
5. **Choose 3 songs** that match the stated taste. Mix one safe pick, one
   slightly new pick, and one wildcard if the user wants discovery.
   Do not recommend songs the user already named as favorites.
6. **Write the answer** in the output format below.
7. **Offer a next step**, such as more songs, a different mood, or a
   longer playlist.

## Output format

Use this structure:

```
Your taste: <one-line summary>

1. "<Song title>" by <Artist>
   Why it fits: <one sentence tied to what the user told you>
   Find it: <link from search results, or search tip>

2. ...
3. ...

Want more like #2, a different mood, or a longer playlist?
```

Rules for the "Find it" line:

- Give a link only if it came from a search result you actually saw.
- Otherwise write a search tip, such as: search "Title Artist" on your
  music app.

## Rules for what not to do

- Do not invent songs, artists, albums, release years, or links. If you
  are not sure a song exists, leave it out or mark it unverified.
- Do not reproduce song lyrics, not even a line. Describe the sound or
  theme in your own words.
- Do not search for or guess private details about a real person.
  Only use what the user tells you.
- Do not ask for sensitive information such as full name, address,
  health, or finances. Taste and mood are enough.
- Do not help download or pirate music. Point to legal streaming or
  purchase options.
- Do not recommend more than 3 songs unless the user asks.
- Do not pad the answer. Keep each reason to one sentence.

## If search is not available

Say so in one line. Recommend only well-known songs you are confident
exist, mark the answer as "from memory, please verify", and give search
tips instead of links.
