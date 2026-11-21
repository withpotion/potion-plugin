# Potion plugin for Cursor and Grok

Potion gives your assistant a podcast feed of your own. The assistant writes or finds what an episode should say, and Potion narrates it. The episode then arrives in the podcast app you already use. Where the host can run work on a schedule, as Grok Bot can with a routine, a daily briefing can turn up every morning without you asking.

This plugin works in Cursor, in Grok Bot (through Cursor's catalog), and in Grok Build. It is published by 9592 Solutions UG (haftungsbeschränkt), the company behind Potion.

## What it adds

- **The Potion server** at `https://api.withpotion.io/mcp/cursor`. It creates feeds, narrates text and articles into episodes, takes audio you already have, and manages what is in each feed. It can also delete feeds and episodes, start account deletion, and return a link to Potion's own plans or billing pages when you ask.
- **A setup skill** for signing in and for adding the feed to a podcast app, which is the step people get stuck on.
- **A shows skill** for making episodes and for shows that keep arriving on a schedule, such as a Grok Bot routine.
- **An upload skill** for putting an audio file from the computer into a feed.

This server answers nothing until you sign in, its tool list included. The same tools, with the same descriptions, can be read without signing in at `https://api.withpotion.io/mcp`, Potion's general address.

## Signing in

There is no key to paste. The server signs in over OAuth: authenticate it from Cursor's MCP settings or from Grok Bot's **Connect apps**. Potion then emails you a 6-digit code, and typing it in connects the server. It also creates your account if you are new.

## What it costs

The plugin is free. New Potion accounts get two hours of narration free, once, which is about twelve days of a ten-minute daily episode. After that, narration needs a paid plan: Plus at $5 a month includes 5 hours per rolling 30 days, and Pro at $12 a month includes 25. Those hours are standard voices; premium voices use them five times as fast. Payment happens on Potion's website and Stripe's checkout, never inside the assistant. Audio you upload yourself never counts against narration. Current plans: `https://api.withpotion.io/plans`.

## Network and data

- From your assistant's side, everything goes to `api.withpotion.io` over HTTPS: the MCP server at `/mcp/cursor`, and the single-use upload address that server hands out.
- Potion's servers fetch the article and audio addresses your assistant gives them. Text sent for narration goes to Potion's text-to-speech providers, which the privacy policy names.
- The plugin holds no credentials. Your sign-in token is kept by Cursor or Grok, and the plugin never reads it.
- The upload skill is written to send only the audio file you chose or asked for, to that upload address.
- Feeds are served from `rss.withpotion.io`, and audio from `audio.withpotion.io`.
- A feed's address is unlisted, not private. Anyone who has it, or a link to an episode's audio, can listen, so think before putting your email or work documents into one.

## Links

- [Terms of Service](https://github.com/withpotion/potion/blob/main/TOS.md) and [Privacy Policy](https://github.com/withpotion/potion/blob/main/PRIVACY.md)
- [API documentation](https://api.withpotion.io/docs)
- [Issues](https://github.com/withpotion/potion/issues) and christo@withpotion.io

## License

MIT. See [LICENSE](LICENSE).
