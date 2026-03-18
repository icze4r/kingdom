# Post Curator 📋

**A Bluesky tool to scan your posts, sort by engagement, and delete the ones you don't want.**

Made by Durandal

an [ICZE4R](https://bsky.app/profile/iczer.one) • [→ Open the tool](https://icze4r.github.io/kingdom/index.html)

---

## What it does

Bluesky gives you no way to bulk-manage your post history. Post Curator fixes that:

1. Logs in with your app password
2. Scans your entire post history (or as much as you want)
3. Shows every post with its engagement stats — likes, reposts, replies, quotes
4. Lets you sort, filter by threshold, and delete selectively or in bulk

Everything runs **entirely in your browser**. No server, no data collection, no tracking.

---

## How to use it

### Online (recommended)

**[https://icze4r.github.io/kingdom/index.html](https://icze4r.github.io/kingdom/index.html)**

### Local

Download `index.html` and open it in any browser. No CORS issues — everything talks directly to Bluesky's API.

---

## Setup

**Step 1 — Get an App Password**

Go to [bsky.app/settings/app-passwords](https://bsky.app/settings/app-passwords) and generate one. Never use your main password with third-party tools. Revoke it any time from the same page.

**Step 2 — Choose what to scan**

Pick a post type before connecting:

| Mode | What it scans |
|---|---|
| Everything | All post types at once |
| Posts only | Original posts — no replies, reposts, or quotes |
| Replies only | Just your replies to others |
| Reposts only | Just things you've reposted |
| Quote posts only | Posts where you quoted someone else |

Switching modes instantly refilters without needing to rescan.

**Step 3 — Connect & Scan**

Enter your handle and app password and hit **Connect & Scan**. The tool fetches up to 500 posts per run. Hit **Load more** to keep going.

**Step 4 — Sort and filter**

Sort by date, likes, reposts, replies, or quotes. Set threshold filters to highlight posts below a certain engagement level — anything below threshold gets flagged in red.

**Step 5 — Select and delete**

Use the checkboxes to pick posts individually, or use the bulk selectors:

- **Select all** — everything visible
- **Select none** — clear selection
- **Select below threshold** — auto-selects everything that doesn't meet your thresholds

Posts show their text (click to expand), image thumbnails if they have media, and a **↗ view on Bluesky** link to see the full post in context before you decide.

Hit **🗑 Delete Selected** to permanently remove them.

---

## Post type badges

Each post is labelled by type:

| Badge | Colour | Meaning |
|---|---|---|
| post | Teal | Original post |
| reply | Orange | A reply to someone |
| repost | Green | Something you reposted |
| quote | Blue | A post quoting someone else |

---

## Filters

| Filter | What it does |
|---|---|
| Min likes | Flag/select posts below this like count |
| Min reposts | Flag/select posts below this repost count |
| Min replies | Flag/select posts below this reply count |
| Min quotes | Flag/select posts below this quote count |
| Show mode | Show all posts, only below-threshold, or only above-threshold |

Thresholds work as AND logic — a post is flagged if it falls below *any* of the thresholds you've set.

---

## Media previews

Posts with images show small inline thumbnails. Click any thumbnail to open the full image in a new tab. Images lazy-load so large lists won't slow your browser down.

---

## Rate limits

- 300ms delay between delete operations
- Bluesky enforces write rate limits — for very large deletion runs, pace yourself and wait a few minutes between sessions if you hit errors
- The scan itself uses read endpoints which have much more generous limits

---

## Privacy & security

- **Your credentials** go directly to `bsky.social` — nowhere else
- **Nothing stored** — no localStorage, no cookies, no analytics
- Single self-contained HTML file — read every line of it
- Deletions are permanent and cannot be undone in bulk — the tool confirms before deleting

---

## Running on GitHub Pages

1. Fork or clone this repo
2. Rename `bluesky-curator.html` to `index.html`
3. Go to **Settings → Pages**
4. Set source to **Deploy from a branch** → `main` → `/ (root)`
5. Save — live within about a minute

---

## Related

- **[Spite — Bluesky BlockBack Tool](https://github.com/icze4r/blockback)** — find accounts blocking you and block them back
- **[Mute Manager](https://github.com/icze4r/mutemanager)** — convert mutes to blocks or clear them
- **[The Eraser](https://github.com/icze4r/tabularasa)** — selectively or completely clear your blocks and mutes

---

## Credits

Built with the [Bluesky AT Protocol API](https://docs.bsky.app) — `getAuthorFeed`, `deleteRecord`.

---

## License

MIT — do whatever you want with it.
