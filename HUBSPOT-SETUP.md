# How to test the form: spin up your own free HubSpot

You don't have Quillstack's HubSpot, so to test a real end-to-end submission you'll wire the page to **your own** free HubSpot account. This is exactly what an SE does to reproduce a customer's setup. It's free, takes ~5 minutes, and no credit card is required.

## 1. Create a free HubSpot account
- Go to **hubspot.com** and sign up for the **free** account (the free CRM / Marketing tools tier is all you need). A personal email is fine.
- Once you're in, note your **Hub ID** (also called the account/portal ID) — it's in the top nav or under Settings. This is your `portalId`.

## 2. Create a form
- Go to **Marketing → Forms → Create form** (or search "Forms").
- Make a simple **embedded form** with a couple of fields (Email + First name is plenty). Publish it.
- HubSpot will give you an **embed code**. It looks like this — the same shape that's already on the page:
  ```html
  <script charset="utf-8" src="//js.hsforms.net/forms/embed/v2.js"></script>
  <script>
    hbspt.forms.create({
      portalId: "XXXXXXX",
      formId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
      region: "naX"
    });
  </script>
  ```
- Copy your **`portalId`**, **`formId`**, and **`region`** out of *your* snippet — you'll use these to point the landing page at your account.

## 3. Run the page locally
- The page is static, so any local server works. From inside `landing-page/`:
  ```
  python3 -m http.server 8000
  ```
  then open **http://localhost:8000** . (Opening the file directly with `file://` can behave differently for scripts — a local server is closer to reality.)
- To test campaign attribution, load it with a query string, e.g. `http://localhost:8000/?utm_campaign=sentinel_launch`.

## 4. Verify a submission actually lands
- Fill the form out and submit it.
- In HubSpot, go to **Contacts** (or the form's **submissions** view) — your test entry should appear within a few seconds.
- A submission that *looks* like it worked on the page but never shows up in HubSpot is **not** fixed. Verifying the data actually arrives is the whole point.

## Don't want to make an account?
Fine — full credit either way. Get the form fully working, then show:
- the **HTTP 200** on the submission request in your browser's **Network** tab (the request to HubSpot's submission endpoint), and the form's success state, and
- a sentence on how you'd confirm the contact landed once you had portal access.

---
*Heads up: free HubSpot forms show a small "Powered by HubSpot" mark. That's expected and irrelevant to this exercise.*
