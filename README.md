# Faithful Witness — The Summer of Justice (August 2026)

*Faithful Witness*, the newsletter of **Love in Action Social Justice Ministry, Inc.**, as a self-hosting web page.

> Love is the answer. Action is the way.

Two files: `index.html` and `images/lia-wordmark-knockout.png`. No build step, no framework. Open it in a browser and it works.

---

## Publish it on GitHub Pages

1. Create a repo, for example `lia-newsletter-august-2026`.
2. Upload `index.html`, the `images/` folder, and this `README.md` to the root. **The `images/` folder must come along or the wordmark will not load.**
3. Go to **Settings → Pages**.
4. Under **Source**, choose **Deploy from a branch**, pick `main` and `/ (root)`.
5. Save. Your page goes live at `https://<username>.github.io/<repo-name>/` in about a minute.

### Custom subdomain (optional)

To serve it at something like `newsletter.loveinactionpaw.org`:

1. Add a file named `CNAME` to the repo root containing only `newsletter.loveinactionpaw.org`.
2. At your DNS host, add a `CNAME` record pointing `newsletter` to `<username>.github.io`.
3. Back in **Settings → Pages**, enter the domain and check **Enforce HTTPS**.

---

## Ready to publish

Every link is wired. Nothing is left as a placeholder.

| Button | Goes to |
|---|---|
| Explore the Campaign (hero + Love Shows Up) | `loveinactionpaw.org/campaign` |
| Report Your Progress (hero) | jumps to `#commitments` |
| Submit Your Update | pre-filled email to `info@loveinactionpaw.org` |
| Register on Teams | Microsoft Teams event registration |
| Share Your Photos | Summer of Justice Shared Content on SharePoint |

> **Check the SharePoint permissions before you publish.** The Shared Content link points into the LIAMasterHub site. Open it in a private browser window while signed out — if it asks for a login, partner churches outside your tenant will hit the same wall. Set the folder's sharing to *Anyone with the link* if you want it publicly reachable from this page.

**Submit Your Update** opens the reader's mail client with a template already in the body — church, city and state, region, milestone, accomplishments, partners, learnings — so updates arrive in a consistent shape instead of freeform paragraphs.

---

## Brand

Colors come from the **2026 LIA Quick Brand Guide**, not from the current `web/` site CSS. The site's `globals.css` is still marked `TODO LIA: confirm final hex codes`, and its red and green do not match the guide.

| Token | Hex | Use |
|---|---|---|
| LIA Black | `#0A0A0A` | Dark section surface |
| LIA Red | `#AD1907` | Primary buttons, rules, headline accent |
| LIA Green | `#206020` | Secondary buttons, event date block |
| Yellow | `#D4B427` | Eyebrows and accents on dark |
| Orange | `#CE781B` | Timeline accent |
| Brown / Light Brown | `#A57C4C` / `#BA9474` | Reserved accents |
| Paper White | `#FFFFFF` | Light section surface |

**Logo.** The sticky header uses `LIA-Wordmark-06-Full-Knockout.png` from your LIA Wordmark PNG Pack, resized from 3501px to 1400px wide (50 KB, retina-ready) and saved to `images/lia-wordmark-knockout.png`. Transparent background, so it sits correctly on the dark nav. It appears **only in the header** — the body of the page carries no logo. To swap it, replace that one file and keep the name.

**Nameplate.** The hero opens with *Faithful Witness* set in Montserrat, letterspaced, flanked by hairline rules. That is the newsletter's masthead; the issue headline ("The Summer of Justice") sits below it. For the next issue, change the headline and leave the nameplate alone.

**Layout.** Everything is centered on a single column. `.prose` is capped at 760px and centered; rules, buttons, cards, chips, and the footer all center with it. If you add a section, wrap the copy in `<div class="prose">` and it inherits the centering automatically.

**Typography.** Gotham is a licensed font and is not available on the web for free, so this page uses the same substitution already in place on the LIA Jotforms:

- **Montserrat** (700–900) for display headlines, standing in for Gotham Bold
- **Inter** for all body copy, per the brand guide
- **Cormorant Garamond Italic** for pull quotes, per the brand guide

All three load from Google Fonts. To self-host them later, download the families and swap the `<link>` for `@font-face` rules.

---

## Editing

Content is plain HTML in semantic sections, each with an `id` that the nav links to:

```
#top           Hero — Faithful Witness nameplate + The Summer of Justice
#summer        July in Indianapolis (combined recap)
#commitments   90-Day Justice Commitments
#loveshowsup   Love Shows Up™
#webinar       Summer Voter Education Webinar Series
```


Section backgrounds alternate using the utility classes `s-dark`, `s-light`, and `s-paper`. If you add a section, alternate the tone so the page keeps its rhythm.

---

## What's built in

- Responsive from 320px up, with a mobile menu
- Scroll-reveal animation that disables itself under `prefers-reduced-motion`
- Skip-to-content link and gold focus rings for keyboard navigation
- OpenGraph and Twitter card tags for link previews
- A print stylesheet, so the page prints cleanly to PDF
- Official LIA full knockout wordmark in the sticky header

## Adding photos

To add convention or backpack photos, drop them in the existing `images/` folder and insert:

```html
<img src="images/your-photo.jpg" alt="Describe what is happening in the photo" style="border-radius:14px;margin-top:2rem">
```

Always write real alt text. Several people on this list use screen readers.
