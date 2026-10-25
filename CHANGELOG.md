# Changelog

Every release is also on the [Releases page](https://github.com/Sigillion-AI/sigillion/releases), with the wheels
and their SHA-256. Watch this repository > Custom > Releases to be told of the next one.

## 0.1.0 (24 October 2026)

The first release: memory for Claude Code, on your own computer.

- Keeps every Claude Code session, word for word (the secrets it recognises replaced by placeholders first; an image
  or a PDF Claude looked at pointed to by its hash, not copied), compressed and sealed: after a compaction, and after
  Claude Code deletes its transcripts.
- Starts each new session with a short brief of where the work stands; Claude recalls and reopens any earlier turn
  when it needs it, and each answer keeps a receipt of exactly what it read.
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
