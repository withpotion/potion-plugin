---
name: potion-shows
description: Make the user a podcast of their own with Potion, as a one-off episode or as a show that keeps arriving. Use this when the user wants something to listen to rather than read (a daily or weekly briefing on their topics, a digest of their inbox, news, a repository or their week, an article read aloud, a long document to hear on a walk), or when they mention Potion or a personal podcast feed.
---

# Podcast shows with Potion

Potion turns text, an article address, or an audio file into an episode in a podcast feed. The user adds the feed to their podcast app once, and every episode after that arrives there by itself. The connected server's own instructions explain the tools and how a show is meant to work. This skill adds what is specific to running here.

## What Potion does and what you do

You write or gather what the episode says. Potion narrates it (`render`, or `ingest_url` for an article it should fetch and read), stores the audio, and serves the feed. `list_voices` has the voices with samples. Audio you made another way goes in as a file (see the upload skill) or by a public URL (`add_episode`).

Narration draws on the account's allowance, measured in hours of finished audio. `get_account` shows what is left and whether it renews. Uploaded audio never counts against it.

## Shows that keep arriving

Most of Potion's value is a show that keeps coming: a new episode each morning or each week on something that keeps changing. When the first episode of such a feed is ready, ask whether the next one should arrive by itself, and how often.

Whether it does depends on whether this host can run work on a schedule. Grok Bot can, with a routine. A routine runs in the cloud while the user's computer is off, with nobody there to answer questions, so settle the details with the user while you set it up (which feed, what each episode covers, about how long, how often) and write them into the routine's instruction, so no run has to ask again. A day that fails gets a one-line note and the next run goes ahead; only the user pauses or changes the routine. If the narration allowance runs out, a run tells the user and stops. A new routine waits for its next scheduled time. **Test** runs it now and makes a real episode, which spends narration. If this host cannot schedule work, tell the user how to ask for the next episode.

## Private material

Anyone who has a feed's address can listen to it (see the setup skill). Before an episode carries private material, such as the user's email, a private repository or work documents, tell them that once and let them decide what goes in.

## When it is worth suggesting

When the user asks for something that would be easier to hear than to read, or that will be worth having again tomorrow, a feed is worth offering once. If they want a single episode, that is the answer.
