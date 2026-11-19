# Neutro B website framework

A simple, static site for **Neutro B**, an indie game and story studio in Bundaberg, Queensland.

This is a framework only: plain HTML and CSS, no build step, ready to style later and to host for free on GitHub Pages. Nothing in this folder has been published or pushed anywhere.

## What’s here

| File | Purpose |
|---|---|
| `index.html` | Home page: about Neutro B, Ozzie Battler, the YouTube channel, and contact |
| `privacy.html` | Ozzie Battler privacy policy (from `cohort-ops/ozzie-battler/privacy-policy-final.md`) |
| `style.css` | Shared stylesheet, with clearly marked spots for colours, a logo, and screenshots |
| `images/` | Empty folder for a logo and game screenshots later |
| `preview.png` | A local screenshot of the home page, for review. Optional to upload |

Relative links are used throughout, so the site works as a GitHub user site (`https://USERNAME.github.io/`) or a project site (`https://USERNAME.github.io/REPO/`).

## How to publish it free on GitHub Pages

These steps are from [GitHub’s Pages documentation](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site). Do not start them until you are ready to go public. This README does not invent a GitHub username — use your own.

1. Create a GitHub account if you do not already have one, at [github.com](https://github.com).
2. Create a new **public** repository.
   - For a site at `https://USERNAME.github.io/`, name the repository **`USERNAME.github.io`** (exactly that).
   - For a site at `https://USERNAME.github.io/REPO/`, the repository can have any name, for example `neutrob-site`.
3. Upload `index.html`, `privacy.html`, `style.css`, and (when you have them) the files in `images/` to the repository root. You can do this in the GitHub website with **Add file → Upload files**, or with `git` later.
4. In the repository, go to **Settings → Pages**.
5. Under **Build and deployment**, set **Source** to **Deploy from a branch**. Choose the `main` branch and the `/ (root)` folder, then save.
6. Wait a minute or two. GitHub will show the live URL on the Pages settings screen. HTTPS is included.
   - User site: `https://USERNAME.github.io/`
   - Project site: `https://USERNAME.github.io/REPO/`
   - Privacy policy: add `privacy.html` to that URL, for example `https://USERNAME.github.io/privacy.html`

A custom domain can be added later in the same Pages settings. It is not required.

**Do not put a home address, phone number, or any family or kids’ details on this site.** Business listings for a Play organisation account can show a legal address and phone separately on Google Play; that is a different decision.

## How to verify the site in Google Search Console

Google Play needs a website you own, verified in Search Console, before you can convert a personal developer account to an organisation account. A Google Doc, a YouTube channel, or a social profile does **not** count. Official Play help: [Verify your website](https://support.google.com/googleplay/android-developer/answer/13205715). Official Search Console help: [Verify your site ownership](https://support.google.com/webmasters/answer/9008080).

Do this **after** the GitHub Pages URL is live, and only when you are ready. Prefer the **same Google account** you use for Play Console, because Play can then approve the website automatically.

1. Open [Google Search Console](https://search.google.com/search-console) and sign in with the Play Console Google account.
2. Choose **Add property**, then **URL prefix**. Paste the exact live site URL, including `https://`.
   - For a user site: `https://USERNAME.github.io/`
   - For a project site, include the repository path: `https://USERNAME.github.io/REPO/`
3. Choose a verification method. The two easiest for GitHub Pages are:
   - **HTML file:** Google gives you a small `google….html` file. Upload that file to the repository **root** (next to `index.html`), wait for Pages to publish it, then click Verify. Visit `https://YOUR-SITE/google….html` in a browser first to confirm it loads.
   - **HTML tag:** Google gives you a `<meta>` tag. Paste it into the `<head>` of `index.html`, upload the change, wait for Pages to update, then click Verify.
4. When Search Console says the property is verified, go to Play Console → **Settings** (or **Manage account**) → **Account details** → **About you**. Enter the same website URL and send the verification request. If that Google account owns the site in Search Console, approval is automatic. If a different account owns it, that owner must approve the request.

The privacy policy URL for Play Console would then be the live `privacy.html` address, for example `https://USERNAME.github.io/privacy.html`. The current policy also exists as a public Google Doc; this page is the version that can live on a site you can verify.

You still need a D-U-N-S number before the organisation account itself can be finished. Website verification is only one of the steps. See `cohort-ops/ozzie-battler/play-org-account-path.md` for the full path.

## Making it look good later

All brand colours live at the top of `style.css` as CSS variables (`--color-bg`, `--color-accent`, and so on). Change those first.

In both HTML pages, the header has a logo placeholder. Replace the `span.logo-placeholder` with:

```html
<img src="images/logo.png" alt="Neutro B" class="logo">
```

On the home page, the three dashed boxes are screenshot placeholders. Replace each `figure.screenshot-placeholder` with an image such as:

```html
<img src="images/ozzie-1.png" alt="Ozzie Battler screenshot">
```

Keep game descriptions factual. If you add a store link, a trailer, or new copy, only use details you have confirmed.

## Local preview

Open `index.html` in a browser, or from this folder run:

```bash
python3 -m http.server 8080
```

Then visit `http://localhost:8080/`.
