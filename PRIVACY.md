# Sigillion privacy note

24 October 2026. Steddy Nova SRL, Brasov, Romania (trade register J2025042808005, CUI 51973580). Contact:
info@sigillion.com.

In short: Sigillion runs on your computer and sends nothing to us or to anyone. No account, no telemetry, no update
check, and its licence is checked offline.

## 1. What Sigillion keeps, and where

- Your Claude Code sessions: what you typed, what Claude answered, the tools it ran and what they returned, and its
  subagents, from the moment you install it; and, when you install it, the history Claude Code still holds (its last
  30 days).
- Secrets (API keys, tokens, passwords, private keys) are replaced by a placeholder before anything is stored. The
  rules find secrets by their known shapes: a secret in a shape they don't know is kept as it is.
- Images and PDFs Claude looked at are not stored: only their size, type, path and a hash.
- Where: in the folder ~/.sigillion on your computer (SIGILLION_HOME and SIGILLION_STORE choose another): the sealed
  store, a search index beside it, logs (which name files, counts and reasons, never the text of a session), and a
  receipt for each answer recall and expand gave.
- Not encrypted yet (encryption of what is kept is planned for the end of 2026): whoever can read your user
  account's files can read the store, as they can read the transcripts Claude Code itself keeps. On Linux,
  Sigillion's folders are open to you alone; on Windows they take the permissions of the folder they are in (your
  user folder, by default).
- To delete everything: `sigillion uninstall`, then delete the folder ~/.sigillion (and the folder SIGILLION_STORE
  names, if you set it). There is nothing to ask us.

## 2. What reaches Anthropic, through Claude Code

- Sigillion gives Claude a short brief when a session starts and after a compaction; the turns Claude recalls when it
  asks; and, when Claude is about to write a script an earlier session already wrote, a note naming that script (its
  name, when it was written, its first line and where it is). These become part of your Claude Code conversation,
  which Claude Code sends to Anthropic as it does the rest of the conversation, under Anthropic's terms and your
  Claude Code settings. Sigillion itself connects to nothing outside your computer.

## 3. The trial and your licence

- The trial is counted on your computer: a small file holds the time of your first and last use. Nothing is sent.
- A licence names its holder (a name and an e-mail address), and is checked on your computer, offline. We keep a
  record of each licence we issue (its holder, plan and dates) to issue it, to answer you about it, and to count the
  500 founder licences; the legal basis is our agreement with you (GDPR Article 6(1)(b)). We keep it for as long as
  the licence can be used, and an invoice for as long as Romanian accounting law requires; anything else is deleted
  when you ask, and deleting it never stops your licence working. We never sell or share it.

## 4. When you join the waitlist or write to us

- You can join through a GitHub issue on Sigillion-AI/sigillion (public: GitHub shows your username and what you
  write), a form run by Typeform or a form run by Google (Google Forms), each under its own terms, or an e-mail to
  info@sigillion.com. We use your name, e-mail address and GitHub username only to tell you about the release and to
  send your licence, and delete them when you ask. The legal basis is your request to join (GDPR Article 6(1)(b),
  steps you asked for before an agreement). We keep them until your founder licence is sent, then only the licence's
  record (section 3); if no licence is sent, we delete them 12 months after the release, or sooner when you ask.
- Founder licences are sent after the release, within your 30-day trial, privately, to the e-mail address you gave
  us. If you joined through a GitHub issue, we ask you for an address first: a licence is never posted in an issue.
  When licences are delivered through a service of ours, this note will say which, and what it receives.
- Paid plans are not on sale yet. Before they are, this note will say how payment works and who processes it.

## 5. Counts you share

- `sigillion status --actions` prints counts, sizes and a date, never the text of a session. They reach us only if you
  paste them somewhere.

## 6. Your rights

- Under the GDPR you may ask to see, correct or delete what we hold about you (a licence record, a place on the
  waitlist), and object to how we use it: write to info@sigillion.com. You may also complain to the Romanian data
  protection authority (ANSPDCP, www.dataprotection.ro) or to the authority where you live.
