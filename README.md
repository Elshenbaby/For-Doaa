# FFCC Meeting Calendar — deploy

Single static page. No build step, no dependencies.

## Deploy (drag and drop)
1. Go to https://vercel.com/new
2. Drag THIS folder onto the page
3. Deploy

## Deploy (CLI)
```
npm i -g vercel
cd vercel
vercel --prod
```

## Files
- `index.html` — the whole app (764 KB): 68 meetings, briefings, AE lists, SDR filters, and the live Google Sheet sync. Fonts, styles and data are inlined; works offline too.
- `vercel.json` — static config, no caching so team members always get the latest version.

## Google Sheet sync
The AE updates write to the Apps Script web app already embedded in `index.html`:

```
https://script.google.com/macros/s/AKfycbz38rgq8oDzfB92z6qEkaBZSqOa3Qao6_kycV25W9sx0LbisYwtmBf96NbRbJOvr4-TXw/exec
```

To point it at a different sheet, replace that URL in `index.html` (search for `AKfycb`) and redeploy. The Apps Script deployment must be set to **Execute as: Me** and **Who has access: Anyone**.
