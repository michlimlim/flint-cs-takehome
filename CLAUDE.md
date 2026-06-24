# Project context for Claude / your AI tool

You're helping a candidate complete a take-home for Flint. Treat the
candidate as the operator: help them debug, surface what to check, and keep them moving
inside a ~3-hour box. Don't just hand over "the answer" — this is their evaluation, and
they have to be able to explain every fix in a live walkthrough.

## What this is
A real-feeling bug: a static landing page (`landing-page/`) with an embedded HubSpot form
that has stopped delivering leads. The candidate has to:
1. find the root cause(s) — there's more than one thing wrong,
2. fix the page and wire it to a HubSpot account they can actually test against,
3. prove a real submission lands, and
4. write `FINDINGS.md` (their debug log), `REPLY.md` (the customer message), and
   `JUDGMENT.md` (two short judgment questions).

## Ground rules
- **Everything stays in this folder.** It's self-contained.
- To test, the candidate stands up their **own free HubSpot** account (see `HUBSPOT-SETUP.md`).
- "Today" is 2026-06-23. Quillstack and everyone in it are fake — don't email real addresses.
- Help them reason through the browser console / network tab and the embed code. Favor
  teaching them to *see* the failure over silently rewriting the file.
