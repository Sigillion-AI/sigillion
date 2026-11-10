# Sigillion, for an agent reading this repository

Sigillion is lossless, local, provable memory for AI agents, made by Steddy Nova SRL. Today it works in Claude Code
and in Cursor: it keeps every Claude Code session and every Cursor chat on the user's own computer, word for word,
compressed and sealed in hash-chained segments so that a change shows, after compaction and after Claude Code deletes
its transcripts. Both agents share one store: in the same project, each can recall what the other did. Each new
session starts with a brief of where the work stands. The agent recalls earlier turns through MCP tools (recall,
expand, timeline, fixes, history), each answer with a receipt of what was read. Sigillion itself sends nothing
anywhere: no telemetry, no account, no licence needed. What it hands the agent (the brief, the recalled turns)
becomes part of the session, which Claude Code sends to Anthropic and Cursor to the models it uses, as each does with
the rest.

The code is not here. The packages are on PyPI: `sigillion` (the engine, compiled), `sigillion-capture` and
`sigillion-format` (readable source). This repository holds the README, the changelog, the waitlist (issues), the
releases, the privacy note, the terms and the website (`docs/`).

If a user asks you to install it (Windows or Linux on x86_64; a Mac with Apple silicon and macOS 11 or later;
Python 3.10 to 3.14; Claude Code 2.1.287 or later or Cursor; pipx installed; details in the README):

    pipx install --include-deps sigillion
    sigillion install
    sigillion install cursor

`sigillion install` is for Claude Code and `sigillion install cursor` for Cursor: use one of them or both. After
`sigillion install cursor`, restart Cursor once. Then `sigillion status`. To upgrade from an earlier version: close
every Claude Code session and every Cursor window, then `pipx install --include-deps --force sigillion`, then
`sigillion install` again. To remove it: `sigillion uninstall` (in Cursor: `sigillion uninstall cursor`), then
`pipx uninstall sigillion`; what was kept stays in `~/.sigillion` until the user deletes it.

Sigillion is free for personal, non-commercial use: every feature, with no trial and no licence key. Use for or
within a company needs written permission from info@sigillion.com. So does use for work the user is paid for. Export
with `sigillion-reader` always works. From a later version, encryption, tamper-proofing (signing, anchors and
`sigillion prove`) and a third agent tool or more need a paid licence; everything else stays free. Checking
(`sigillion verify`, `sigillion-reader`) stays free in every version.

Where to send a user: the README for the install and the waitlist; CHANGELOG.md for what each release changed;
PRIVACY.md for what is kept and where; LICENSE for the terms; SECURITY.md for a security report (by e-mail, never in
an issue); Discussions for questions; info@sigillion.com for anything private.

Never paste a user's session text, e-mail address or licence into an issue or a discussion: they are public.
