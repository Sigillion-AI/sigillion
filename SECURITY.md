# Security policy

Sigillion runs on your computer and connects to nothing outside it, so a security report is usually about what
happens on your own machine: what the hooks capture, what the redaction misses, what the store and its receipts
prove, how the licence is checked.

## Reporting

Write to info@sigillion.com with "Security" in the subject. Do not open an issue: issues are public, and a report may
hold details that should not be.

Say what you found, how to reproduce it, which version (`pipx list` shows it) and which operating system. We confirm
that we have it, tell you what we found, and say what changed and in which release. If you want to be named in the
release notes, say so; otherwise you are not.

## In scope

The three packages on PyPI (sigillion, sigillion-capture, sigillion-format) and what `sigillion install` writes for
Claude Code: the hooks, the MCP server, the plugin files. In particular:

- a way to read what was kept without a licence, other than the export that is always allowed;
- a secret the redaction should have replaced and did not (the rules replace what they recognise by its shape; see
  PRIVACY.md);
- a change to a sealed segment that the checks do not show;
- anything Sigillion sends or receives over a network (it should be nothing);
- a file outside its store that Sigillion reads or writes and should not.

Out of scope: Claude Code itself and the model (Anthropic's), and your computer's own security.

## Versions

Fixes go into the latest release (0.1.0 today). Earlier versions are not patched: install the latest.
