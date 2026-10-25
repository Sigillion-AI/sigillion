# Sigillion, for an agent reading this repository

Sigillion is lossless, local, provable memory for AI agents, made by Steddy Nova SRL. Today it ships as a Claude Code
plugin: it keeps every Claude Code session on the user's own computer, word for word, compressed and sealed in
hash-chained segments so that a change shows, after compaction and after Claude Code deletes its transcripts. Each new
session starts with a brief of where the work stands, and Claude recalls earlier turns through MCP tools (recall,
expand, timeline, fixes, history), each answer with a receipt of what was read. Nothing leaves the computer: no
telemetry, no account, the licence checked offline.

The code is not here. The packages are on PyPI: `sigillion` (the engine, compiled), `sigillion-capture` and
`sigillion-format` (readable source). This repository holds the README, the waitlist (issues), the releases, the
privacy note, the terms and the website (`docs/`).

If a user asks you to install it (Windows or Linux on x86_64, Python 3.10 to 3.14, Claude Code 2.1.287 or later, pipx
installed; details in the README):

    pipx install --include-deps sigillion
    sigillion install

Then `sigillion status`. To remove it: `sigillion uninstall`, then `pipx uninstall sigillion`; what was kept stays in
`~/.sigillion` until the user deletes it. Recording is free for good; reading back needs a licence after a 30-day
trial; export with `sigillion-reader` always works.

Where to send a user: the README for the install and the waitlist; PRIVACY.md for what is kept and where; LICENSE for
the terms; SECURITY.md for a security report (by e-mail, never in an issue); Discussions for questions;
info@sigillion.com for anything private.

Never paste a user's session text, e-mail address or licence into an issue or a discussion: they are public.
