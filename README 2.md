# Wedding invitation site

Three tap-through invitation designs plus a guest-link tool. Plain static files, no build step.

| Page | What it is |
|---|---|
| `/porcelain` | Blush paper, embossed florals, gatefold doors with a seal |
| `/lubugo` | Barkcloth background, envelope with gold wax seal |
| `/emerald` | Green velvet, art deco frame, gold ribbon to untie |
| `/links` | Paste guest names, get a personal link + WhatsApp message for each |
| `/` | Opens the Porcelain design (change in `vercel.json`) |

## 1. Edit the wedding details
Everything lives in **`config.js`**: names, families, date/time, venues, schedule, dress code,
RSVP deadline and the WhatsApp number that receives replies (`rsvpPhone`, digits only, e.g. `256772123456`).
All three designs read from this one file.

## 2. Deploy to Vercel
**CLI (fastest):**
```bash
npm i -g vercel
cd wedding-invitations
vercel          # first time: log in, accept defaults ("Other" framework, no build command)
vercel --prod   # publish to your production URL
```
**GitHub:** push this folder to a repo, then on vercel.com choose *Add New → Project*, import the repo,
framework preset **Other**, leave build command empty, and deploy.

## 3. Send invitations
Open `https://<your-project>.vercel.app/links`, pick a design, paste guest names and tap
**Send on WhatsApp** next to each guest. Each link looks like:
`https://<your-project>.vercel.app/emerald?guest=Grace%20Nakato`

## Notes
- To use only one design, change the `/` rewrite in `vercel.json` and share that.
- A custom domain (e.g. `joeandjane.ug`) can be added under the project's *Settings → Domains*.
- RSVP replies arrive as WhatsApp messages; there is no database.
