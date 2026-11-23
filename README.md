# HD Physiotherapy — hdphysio.ca

A one-page site for Harjit Dhanda's physiotherapy practice. Booking buttons use two labels throughout: "Book an appointment" opens Harjit's Jane page (the one in "Your first session" opens the 60-minute first session directly), and "View availability" opens Jane's month view. Both open in a new tab.

## What's in here

| File | What it is |
| --- | --- |
| `index.html` | The whole site. Styles, logo and fonts are all built in, so it also opens correctly straight from a folder |
| `CNAME` | Tells GitHub Pages to serve the site at `hdphysio.ca` |
| `FONT-LICENSE.txt` | Licence for the Archivo typeface used on the site (free, OFL) |
| `favicon.svg`, `favicon-32.png`, `apple-touch-icon.png` | Browser tab and phone home-screen icons |
| `photos/` | Optional background for the top of the page (see `photos/README.txt`) |
| `harjit.jpg` | Harjit's photo in the "Meet Harjit" frame |
| `og-image.jpg` | The preview image when the link is shared in texts and social posts |

## Publish on GitHub Pages

1. Create a new **public** repository (for example `hdphysio.ca`) and upload everything in this folder to the root of the repo (`index.html` must sit at the top level, not inside another folder).
2. In the repo, go to **Settings → Pages**. Under "Build and deployment", choose **Deploy from a branch**, branch `main`, folder `/ (root)`, then **Save**.
3. Under "Custom domain", make sure it reads `hdphysio.ca` (from the `CNAME` file), then **Save**. Do this before changing DNS.

## Point hdphysio.ca at GitHub (CanSpace)

In the CanSpace client area: **Domains → Manage DNS** (if there's no zone yet, click **Add new zone** and add `hdphysio.ca`). The nameservers must be `dns1.canspace.ca` and `dns2.canspace.ca`. If the domain is on a CanSpace hosting plan, use **cPanel → Zone Editor** instead.

Delete any existing A, AAAA or CNAME records for `hdphysio.ca` and `www` (parking pages, old hosting), but leave MX and TXT records alone so email keeps working. Then add:

| Type | Name | Value |
| --- | --- | --- |
| A | hdphysio.ca | 185.199.108.153 |
| A | hdphysio.ca | 185.199.109.153 |
| A | hdphysio.ca | 185.199.110.153 |
| A | hdphysio.ca | 185.199.111.153 |
| AAAA | hdphysio.ca | 2606:50c0:8000::153 |
| AAAA | hdphysio.ca | 2606:50c0:8001::153 |
| AAAA | hdphysio.ca | 2606:50c0:8002::153 |
| AAAA | hdphysio.ca | 2606:50c0:8003::153 |
| CNAME | www | `<github-username>.github.io` |

The AAAA records are optional but recommended. For `www`, use the GitHub username only, without the repository name.

DNS can take up to 24 hours. Once the GitHub Pages screen shows the DNS check passing, tick **Enforce HTTPS** (it can take a while to become available).

## Common edits

**Change Harjit's photo.** His photo is `harjit.jpg`, next to `index.html`. To swap it, replace that file with a new photo of the same name (a 4:5 portrait at least 800 × 1000 px looks sharpest). If the file is ever missing, the frame shows the HD logo instead.

**Background photo or video.** Optional: see `photos/README.txt` for adding a looping video or wide photo behind the headline.

**Conditions strip.** The scrolling list of conditions under the headline is in `index.html` (search for `Common conditions`). Edit the list so it matches what Harjit actually treats.

**Prices.** Search `index.html` for `price-row`. Each line is one appointment with its length and fee, copied from Jane in November 2026. Update them here whenever they change in Jane.

**Direct billing list.** Search `index.html` for `insurers`. Each insurer is one `<li>` item; add or remove names to match the plans Harjit bills directly.

**Common questions.** Search `index.html` for `<details>`. Each block is one question and answer.

**Venue name and unit.** The site says "HD Physiotherapy at Journey Athletics HQ" and uses unit #100. Confirm both once the unit number is final (search for `Journey Athletics` and `#100`).

**Booking links.** "Book an appointment" goes to `https://harjitdhandaphysio.janeapp.com/#staff_member/1`, and "View availability" goes to `https://harjitdhandaphysio.janeapp.com/locations/harjit-dhanda-physio/book/month`.
