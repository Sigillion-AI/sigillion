# Sigillion

> **Remember everything. Read almost nothing. Prove all of it.**

[![PyPI](https://img.shields.io/pypi/v/sigillion?label=PyPI&color=3f6b5e)](https://pypi.org/project/sigillion/)
![Python 3.10 to 3.14](https://img.shields.io/badge/Python-3.10%20to%203.14-23262b)
![Windows and Linux](https://img.shields.io/badge/Windows%20%7C%20Linux-x86__64-23262b)
[![Website](https://img.shields.io/badge/sigillion.com-website-7f5520)](https://sigillion.com)

[Website](https://sigillion.com) | [PyPI](https://pypi.org/project/sigillion/) | [Releases](https://github.com/Sigillion-AI/sigillion/releases) | [Changelog](CHANGELOG.md) | [Privacy](PRIVACY.md) | [Terms](LICENSE) | [Security](SECURITY.md) | [For agents](AGENTS.md)

Sigillion is memory for AI agents, made by Steddy Nova SRL. It keeps the whole record of what an agent and a person did,
word for word, on your own computer; compressed, so that a model can skim weeks of work in a few hundred tokens and open
the full text only where it needs it; sealed, so that every record can be checked to show it was not altered. No
telemetry: Sigillion itself sends nothing anywhere. What it hands Claude becomes part of your Claude Code session,
which Claude Code sends to Anthropic as it does the rest.

## One engine, in order

1. **Claude Code first.** Today Sigillion ships as a Claude Code plugin: every session is kept after compaction and after
   Claude Code deletes its transcripts, and Claude searches and reopens its own history while it works. Claude Code is
   where every feature is built, measured and proved on real work. It is the first step, not the whole idea.
2. **Every AI model and agent tool next.** The engine does not depend on one model. The same sealed memory will sit under
   other models and the tools people already use (coding agents, agent frameworks, assistants), with an SDK for anyone
   who builds agents.
3. **Then the fields where the record must stand: legal and finance.** The same store, with a pack for each field: its
   citations and terms, its redaction rules, and receipts that show what the model did and when, for work a client, a
   regulator or a court may ask about.

Each step comes after the one before has proved itself with other people's numbers, not before.

## Install

Sigillion 0.1.0 is out on PyPI, a few days earlier than the Friday 30 October we had told the waitlist.

You need:
- Windows or Linux on a 64-bit Intel or AMD processor (x86_64). Not yet: macOS, ARM processors, Alpine Linux.
- Python 3.10 to 3.14. Python 3.15 needs a C compiler until zstandard, which Sigillion uses, publishes a package for
  it; with 3.14 installed beside it, `pipx install --include-deps --python 3.14 sigillion` needs none (on Linux with
  a pipx older than 1.6: `--python python3.14`).
- Claude Code 2.1.287 or later. To update it: `claude update`; installed with WinGet:
  `winget upgrade Anthropic.ClaudeCode`.
- pipx, then a new terminal:
  - Windows: `py -m pip install --user pipx`, then `py -m pipx ensurepath`.
  - Ubuntu 23.04 or later, Debian 12 or later: `sudo apt install pipx`, then `pipx ensurepath`.
  - Other Linux: `python3 -m pip install --user pipx`, then `python3 -m pipx ensurepath`.
  - Anything else: [pipx's installation page](https://pipx.pypa.io/stable/installation/).

Then two commands:

    pipx install --include-deps sigillion
    sigillion install

`sigillion status` shows what is kept; `sigillion --help` lists every command. To take it out: `sigillion uninstall`,
then `pipx uninstall sigillion`; what was kept stays in `~/.sigillion` until you delete it.

- Recording is free for good; reading sessions back needs a licence after a 30-day trial; exporting everything kept
  always works, with or without one.
- How it ships: the engine compiled; the storage format and the capture (what touches your transcripts) as readable
  source. Sigillion is not open source: all rights are reserved by Steddy Nova SRL.
- Search by meaning is being worked on: today recall finds words, a prefix or a handle. This page says so as soon as
  it lands.
- Privacy: [PRIVACY.md](PRIVACY.md). The terms: [LICENSE](LICENSE). Security reports: [SECURITY.md](SECURITY.md),
  by e-mail, never in an issue.

## Founder licences

- **The first 500 people on the waitlist get a founder licence:** Pro for one person, free for life, in the order
  people joined (spam and duplicates removed).
- Licences are sent within your 30-day trial, privately, never in an issue: no key is needed to start. If you joined
  through an issue, we reply there and ask you to write to info@sigillion.com with your GitHub username, so the
  licence can go to you privately.
- To hear about new releases: Watch this repository > Custom > Releases.

## Join the waitlist

Open a new issue and choose "Join the Sigillion waitlist".

Issues are public: do not write e-mail addresses, client names, code or anything private.

Rather not sign up in public? Write to info@sigillion.com with your GitHub username: you join the same list.

If you want, tick that you'd share Sigillion's results: once a week you paste the counts Sigillion prints about what it
did for you (`sigillion status --actions`: how many answers came from memory, how much of your history they read, and
the like). Numbers only, never the text of your sessions, and only what you choose to paste. It helps us show what
Sigillion does.

If you write to us, we use your address only to answer you and to send your licence, and delete it when you ask.

The code is not in this repository: the packages are on PyPI (sigillion, sigillion-capture, sigillion-format). This
repository holds the waitlist, the releases, the privacy note, the terms and the website (`docs/`,
served at sigillion.com).

Questions: [Discussions](https://github.com/Sigillion-AI/sigillion/discussions). Private matters: info@sigillion.com.
Sigillion is made by Steddy Nova SRL.
