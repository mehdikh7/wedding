# Wedding RSVP

Static page (`index.html`) + Google Apps Script backend (`Code.gs`) writing to a Google Sheet.

## Deploy
1. New Google Sheet > Extensions > Apps Script. Paste `Code.gs`, save, run `setup()` and approve.
2. Fill the **Config** tab: `party_address`, `notify_email`, `site_url` (after step 4).
3. Deploy > New deployment > Web app. Execute as **Me**, access **Anyone**. Copy the `/exec` URL.
4. In `index.html`, edit the `CONFIG` block: paste `apiUrl`, names, times, food options.
5. Push `index.html` (+ `og.jpg`, a 1200x630 preview image) to a GitHub repo > Settings > Pages > deploy from `main`.
6. Optional personal links: add names to the **Guests** tab, run `makeLinks()`, send each guest their link.

## Rules of thumb
- Code change in Apps Script: Manage deployments > Edit > New version (keeps the URL).
- `FOOD_OPTIONS` in Code.gs must match `CONFIG.foodOptions` in index.html (server rejects unknown options).
- Set `rsvp_open` to FALSE in Config to close replies.
- Leave `apiUrl` empty to test the page locally in demo mode.
