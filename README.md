# SocialFlow AI: Landing Page

A static, single-page website (HTML, CSS and vanilla JavaScript). It needs no build step, framework or database, so it can be hosted free on GitHub Pages.

## Files
| File | Purpose |
|---|---|
| `index.html` | The whole site: content, styles, interactive previews and contact form |
| `og-image.png` | Preview image shown when the link is shared on WhatsApp, LinkedIn, Facebook or X |
| `robots.txt`, `sitemap.xml` | Help search engines find and index the site |

## 1. Deploy to GitHub Pages (free)
1. Go to https://github.com/new and create a **public** repository called `SocialFlowAI` under `Yomie-commits`.
2. Choose **Add file → Upload files**, drag in all the files, then select **Commit changes**.
3. Open **Settings → Pages**. Under **Build and deployment**, set Source to **Deploy from a branch**, Branch to **main**, folder **/ (root)**, then **Save**.
4. After 1–2 minutes the site is live at **https://yomie-commits.github.io/SocialFlowAI/**

Command-line alternative:
```bash
cd SocialFlowAI
git init && git add . && git commit -m "SocialFlow AI landing page"
git branch -M main
git remote add origin https://github.com/Yomie-commits/SocialFlowAI.git
git push -u origin main
```
Then do step 3.

**Different username, repo name or custom domain?** Find and replace `https://yomie-commits.github.io/SocialFlowAI/` in `index.html`, `robots.txt` and `sitemap.xml`.

Other hosts: **Netlify Drop** (https://app.netlify.com/drop) gives you a live URL instantly when you drag the folder in. On **InfinityFree**, upload the files to `htdocs`.

## 2. Contact form
Out of the box, a valid submission shows **Send on WhatsApp** and **Send by email** buttons with all the details pre-filled. This needs no setup.

To have submissions emailed to you automatically:
1. Create a free form at https://formspree.io using your business email.
2. Copy the endpoint (for example `https://formspree.io/f/abcdwxyz`).
3. In `index.html`, find `formEndpoint: ""` at the top of the `<script>` and paste the endpoint between the quotes.
4. Re-upload `index.html`. If Formspree is ever unreachable, the form falls back to the WhatsApp and email buttons.

Spam and security: hidden honeypot field (`_gotcha`, also recognised by Formspree), validation, length limits, and user input is never inserted as HTML. GitHub Pages serves the site over HTTPS.

## 3. Editing content
- **Prices:** search for `KES 10,000`, `KES 25,000` and `KES 45,000` in `index.html`.
- **WhatsApp and email:** update the `CONFIG` block at the top of the script, then search the HTML for the number and address. They also appear in links and in the SEO data in `<head>`.
- **Caption studio examples:** the `CAPS` object in the script holds the sample captions for each platform and tone.
- **How it works details:** the `STEPS` object in the script.

## 4. SEO after going live
- Add the site in Google Search Console (https://search.google.com/search-console) and submit `sitemap.xml`.
- Link to the site from your Google Business Profile, LinkedIn and WhatsApp Business profile.
- Already included: page title and description, Open Graph and Twitter preview tags, canonical URL, structured data (ProfessionalService and FAQPage), semantic headings, sitemap and robots.txt.

## Testing done before delivery
Tested in headless Chrome at desktop (1366px) and mobile (390px) sizes:
- All in-page navigation links resolve. The active menu item follows scrolling, and the mobile menu opens and closes.
- Hero dashboard: sidebar views, post previews, approval toggles and the date-range switch all work, with mouse and keyboard.
- Product previews: platform filter, caption studio (platform and tone), approval queue counters and report metric switch all work.
- Feature examples expand. Clicking a how-it-works stage shows its details, and Previous/Next and autoplay work.
- Package recommender: updates live, highlights the matching card and pre-fills the contact form.
- FAQ search filters questions and shows a message when nothing matches.
- Contact form: checks required fields, validates email and phone, requires consent, and has a character counter. The honeypot blocks bots, and the WhatsApp and email links carry the details. Formspree mode was tested against a mock endpoint.
- External links (WhatsApp, email, LinkedIn) point to the right addresses. Web links open in a new tab with `noopener`.
- No JavaScript errors and no horizontal scrolling on mobile.
