---
name: potion-setup
description: Connect the Potion server, sign the user in, and get their feed into a podcast app. Use this when the Potion server shows as needing authentication or lists no tools, when a call is refused or says Potion is not signed in, when the user has just installed this plugin, or when they hold a feed address and do not know what to do with it. Also when someone asks how to subscribe, where the RSS address goes, or why a new episode is not on their phone.
---

# Setting Potion up

Two things happen once: the server is signed in, and the feed is added to a podcast app. Neither needs an API key.

## Signing in

The `potion` server signs in over OAuth, and it answers nothing until it is signed in: not even its tool list. A server that shows as needing authentication, or that lists no tools, is waiting for the sign-in, not broken. In Cursor the sign-in is the server's login or Connect control in the MCP settings. In Grok Bot it is **Authenticate** on the Potion app under **Connect apps**, or the **Connect** card in the chat.

The sign-in page asks for an email address and emails a 6-digit code. Typing the code in both connects the server and creates the account if it is new. If the sign-in later lapses, Potion refuses again with the same request to sign in, and signing in again fixes it.

## Getting the feed into a podcast app

This is where people get stuck. Most podcast apps can add a feed by its address, though each puts that option somewhere different. Spotify's app cannot add one.

The feed's `rss_url` brings nothing to the user's phone until it is added to an app as a private or custom feed. Opened in a web browser, the same address shows a page made for this step: a QR code that carries it from a computer to a phone, and buttons for the common apps. Sending the user that link is usually the shortest route. If they name an app, look up that app's current steps. Potion keeps no per-app instructions. `get_feed` reports whether a podcast app has fetched the feed yet, which is a good sign the step worked.

Put an episode in before they add the feed, because many apps treat an empty feed as broken.

The address is unlisted, not private. It is long and random, and podcast directories are asked not to list it, but anyone who has the address, or a link to one of its episodes' audio, can listen. Tell the user that once, so they do not post it.

An episode's `share_url` plays in a browser, for someone who wants to hear it before the app step is done.
