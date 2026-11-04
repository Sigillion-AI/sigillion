# Changelog

Every release is also on the [Releases page](https://github.com/Sigillion-AI/sigillion/releases), with the wheels
and their SHA-256. Watch this repository > Custom > Releases to be told of the next one.

## 0.1.2 (4 November 2026)

The Mac with Apple silicon.

- Sigillion runs on a Mac with Apple silicon (M1 or later) and macOS 11 or later: one engine wheel for every Python
  from 3.10 (`macosx_11_0_arm64`), built, installed and tested on GitHub's macOS 15 runners with Python 3.10 to 3.15.
  Not yet: a Mac with an Intel processor.
- On macOS every durable write asks the drive itself to write the bytes (`F_FULLFSYNC`, as SQLite does); the plain
  `fsync` only where the volume refuses it. macOS's own `fsync` hands the bytes to the drive's cache, which a power
  cut can lose. Nothing changes on Windows or Linux.
- The brief's clock reads the system's processes on macOS too, so a start that takes too long is said there as on
  Windows and Linux.
- A store whose path is longer than the system allows is refused in one line with the system's own words. On
  Windows, past 32,767 UTF-16 units, 0.1.1 said a bug instead.
- When Claude Code is too old, `sigillion install` names Homebrew's update command on a Mac
  (`brew upgrade claude-code`), as it names WinGet's on Windows.
- Cursor on a Mac is not measured yet. The engine's PyPI page still says Cursor was measured on Windows.

Packages: sigillion 0.1.2 (the engine, compiled), sigillion-capture 0.1.2 and sigillion-format 0.1.2 (readable
source). Windows and Linux (x86_64), macOS (Apple silicon).

```
4cf47ed1881f6dbdbcb1e7c5f521e4ddd4ed9d6a5bedd23ded2e657718c6168b  sigillion-0.1.2-cp310-abi3-macosx_11_0_arm64.whl
9422edd78ac9fe35b8e187a5a2adef316bde387449192a36d4be1e6d69b56abc  sigillion-0.1.2-cp310-abi3-win_amd64.whl
baade70bb3bc74aaf196e5ee0f3572a1e3bdef2df1e54c73e6e651ba37daf65a  sigillion-0.1.2-cp310-abi3-manylinux_2_28_x86_64.whl
00d7d878f1f1f2063e8aa87ee8b1e6c292b0efe0d3b412ed26ff00581ab7f9f3  sigillion_format-0.1.2-py3-none-any.whl
951198f648dfad24f322ddb65c413b65309931a7250169adaf4ee38016da4018  sigillion_capture-0.1.2-py3-none-any.whl
```

## 0.1.1 (3 November 2026)

Cursor beside Claude Code, in one store. Free for personal use, with no trial.

- Cursor: `sigillion install cursor` sets Sigillion up in Cursor (restart Cursor once after it). Sigillion keeps your
  Cursor chats: what you typed, what the agent answered and thought, the tools it ran and what they returned, the
  files it changed (as they were before and after each edit) and the long outputs it saved to files. It reads them
  from Cursor's own database, read-only. It brings in every chat Cursor still holds. A chat's first prompt comes with
  the brief. Measured on Cursor 3.27 on Windows.
- One store for both agents: in the same project, Cursor's agent can recall what Claude Code did. Claude can recall
  what you did in Cursor.
- Free for personal, non-commercial use: every feature, with no trial and no licence key. 0.1.0's 30-day trial is
  gone. Use for or within a company needs our written permission (info@sigillion.com). The terms: LICENSE,
  Version 2.
- Redaction, rules version 5: a secret inside a string that is itself inside a string (a tool's result kept as JSON,
  by Cursor and by Claude Code) is now replaced like any other. 0.1.0 read one level only. A segment sealed by 0.1.0
  is never changed (lossless), so it may still hold such a secret.
- A Claude Code request line's hash is keyed when a secret in its message was replaced. Before, the plain hash let
  anyone with the store confirm a guess of the secret.
- Redaction's time grows with the number of secrets in a text, not with its square: 40,000 keys in one text take
  ten times 4,000's time, not about a minute.
- Upgrades: an older Sigillion still running leaves alone a search index a newer one made. Close every Claude Code
  session and every Cursor window before you upgrade: 0.1.0 cannot be changed and still rebuilds a newer index.
- Fixed in Cursor's capture: a prompt edited and sent again could stop its chat from ever sealing again; a turn
  Cursor wrote again in place, with more or fewer characters, is sealed by the next sweep; a time the system's clock
  refuses no longer sets a chat aside; a chat whose brief ran out of time is briefed at its next prompt; Cursor's
  hooks file keeps its version and its mode; Sigillion never writes over a change Cursor made meanwhile; a window on
  a network share or a WSL folder is told why Sigillion does not open it.
- `sigillion status` before any store names both agents. `sigillion uninstall` says where the memory is when the
  plugin's files are in another folder.

Packages: sigillion 0.1.1 (the engine, compiled), sigillion-capture 0.1.1 and sigillion-format 0.1.1 (readable
source). Windows and Linux (x86_64).

```
2b4c0ac7c11226cd9202a01c7ebe9385253c9d66d42ecb4aff0b87885a319aca  sigillion-0.1.1-cp310-abi3-win_amd64.whl
a091bb9cfa2de7c933e3b5359c3321a81c7f170a766ae5960471388e5cb4a493  sigillion-0.1.1-cp310-abi3-manylinux_2_28_x86_64.whl
5d483332b68e51a7cf771c0b8aa7bd1149bda66ae9645bca1d7c249a89ecf35a  sigillion_format-0.1.1-py3-none-any.whl
200dc441a3b25835d9a5a3d3f7a5c8d7339019bade8e4fd8b2dfca32e70c6c6a  sigillion_capture-0.1.1-py3-none-any.whl
```

## 0.1.0 (24 October 2026)

The first release: memory for Claude Code, on your own computer.

- Keeps every Claude Code session, word for word (the secrets it recognises replaced by placeholders first; an image
  or a PDF Claude looked at pointed to by its hash, not copied), compressed and sealed: after a compaction and after
  Claude Code deletes its transcripts.
- Starts each new session with a short brief of where the work stands; Claude recalls and reopens any earlier turn
  when it needs it; each answer keeps a receipt of exactly what it read.
- `sigillion status --actions`: four lines of counts of what Sigillion did for you, safe to paste anywhere.
- Recording is free for good; reading back is free for 30 days, then needs a licence; export always works.
- Windows and Linux (x86_64), Python 3.10 to 3.14, Claude Code 2.1.287 or later. Not yet: macOS, ARM processors,
  Alpine Linux; Python 3.15 needs a C compiler until zstandard publishes a package for it.
- Not yet: encryption of what is kept; search by meaning (being worked on).

Packages: sigillion 0.1.0 (the engine, compiled), sigillion-capture 0.1.0 and sigillion-format 0.1.0 (readable source).

```
3805b6e3cac756d3abfba9346155012a49464481579eb1e14815a5644f7977df  sigillion-0.1.0-cp310-abi3-win_amd64.whl
a9a5315b33d1e1551030c8e9ff3d6c46e74df9ddec7c8d9f64dfe53f983da19e  sigillion-0.1.0-cp310-abi3-manylinux_2_28_x86_64.whl
66af162007ce2c6e37eaa207a5cc5311714ae2c350dd4f4e3ee675b0e1e9d1ba  sigillion_format-0.1.0-py3-none-any.whl
eb3ab3a1d6f79ae8b9edf5dc37420df4474e493b7144e02566ec46243cb60e3e  sigillion_capture-0.1.0-py3-none-any.whl
```
