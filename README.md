# Flint — take-home: the dead lead form

Thanks for doing this. This mirrors a real, recurring first-90-day moment on our team: a customer launches a page, traffic is flowing, and **no leads are showing up**. Your job is to get into the guts, find out why, fix it, prove it's fixed, and tell the customer what happened — like a person, not a ticket.

**Time box: ~2–3 hours.** Stop around 3 hours even if it isn't perfect. We'd rather see how you work than a flawless submission.

**Use whatever tools you'd actually use on the job** — Claude, dev tools, Google, the HubSpot docs. We build *with* AI here; we're scoring your judgment and how you drive the tools, not whether you memorized HubSpot's embed API.

> **You can ask us questions.** Just reply to the email that sent you this — treat us the way you'd treat a teammate channel. The complaint below is vague on purpose (they always are). If something's ambiguous, ask.

---

## The situation

You've picked up an urgent message from **Priya**, the demand-gen marketer at **Quillstack** (a customer — context in `CONTEXT.md`):

> *"We launched our Sentinel waitlist page yesterday and I've got Google Ads pointing at it. We've had a few hundred clicks and **zero leads in HubSpot.** I'm freaking out a little — this is our launch. Can someone look ASAP?? The page is at the link, I zipped the files for you too."*

The page she's talking about is in **`landing-page/`** (`index.html` + `styles.css`). In production this would be a Flint page; for this exercise you've got the raw exported page so you can actually get under the hood. It has a HubSpot form embedded on it that's supposed to send every signup into Quillstack's HubSpot.

**It isn't working.** Open it, figure out why — there may be more than one thing wrong — and fix it.

### About testing it against HubSpot
The page is wired to **Quillstack's** HubSpot portal, which you don't have access to. So to actually test a real end-to-end submission, **stand up your own free HubSpot account and point the form at it** — exactly what you'd do on the job to reproduce a customer's setup. Step-by-step instructions are in **`HUBSPOT-SETUP.md`** (takes ~5 min, free, no credit card). "Fixed" means **a real test submission lands as a contact in your HubSpot** — not just that the form appears.

> If you'd rather not create a HubSpot account, that's fine: get the form fully working, show the **successful submission request (HTTP 200)** in your browser's network tab + the form's success state, and describe how you'd confirm the contact landed in-portal. Either path is full credit.

---

## What to deliver

A repo or zip containing:

1. **The fixed `landing-page/`** — wired to your own HubSpot — **plus proof it works** (a screenshot of the test contact in HubSpot, or the 200 submission + success state).
2. **`FINDINGS.md`** — your debug log. For *each* thing you found: the symptom, **how you tracked it down** (what you looked at — console, network tab, the code), the root cause, and your fix. Keep it concrete; this is the part we read most closely.
3. **`REPLY.md`** — the actual message you'd send **Priya**. She's stressed, she's not technical, and there's ad spend burning. Ready to send — no `[brackets]`.
4. **`JUDGMENT.md`** — short answers (a few sentences each) to:
   - **a.** The page ran paid traffic for ~24 hours with a broken form. What do you tell Quillstack about the **leads and the ad spend** during that window — and what do you actually *do* about it?
   - **b.** Of the issues you found, which would you **fix yourself** and which would you **escalate to Flint engineering** — and why? (There's no single right answer; we want your reasoning on where the line is.)
5. A few of the **key prompts / your AI session**, so we can see how you drove your tools.

If you advance, the final round is a **paid, hands-on build session** in Flint — you'll actually import a site, build pages, and wire integrations up live with us. The real work.

Have fun digging in.
