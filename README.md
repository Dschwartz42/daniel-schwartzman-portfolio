# Daniel Schwartzman — Portfolio

Personal portfolio site. Static HTML/CSS/JS, no build step.

## Preview locally

```bash
# Option 1 — just open the file
open index.html

# Option 2 — serve it (better for fonts/assets)
cd Danielportfolio && python3 -m http.server 8080
# then visit http://localhost:8080
```

## Fill in placeholders

All placeholder text is wrapped in `<span class="ph">[...]</span>` and shows up with a red dashed underline in the browser. Replace each one:

| Placeholder | What to put there |
|---|---|
| Hero intro line | Your one-liner about yourself |
| About paragraphs (3×) | Your bio — 2–3 short paragraphs |
| LinkedIn URL | Your linkedin.com/in/handle |
| Sandbag Sundays links | Live demo URL + GitHub repo URL |
| Chronoshift links | Live demo URL + GitHub repo URL |

## Swap the profile photo

1. Drop your headshot at `assets/profile.jpg` (or `.png` / `.webp`)
2. In `index.html`, change `src="assets/profile.svg"` to `src="assets/profile.jpg"`
3. Done — it fills the circular frame automatically

## Add project screenshots

Replace the gradient mockup cards with real screenshots:
1. Take a screenshot of each app and drop it in `assets/` (e.g. `sessn-screenshot.png`)
2. In `index.html`, replace the `<div class="proj-visual v-sessn">` block with:
   ```html
   <div class="proj-visual">
     <img src="assets/sessn-screenshot.png" alt="Sessn app screenshot" style="width:100%;height:100%;object-fit:cover;" />
   </div>
   ```

## Add your resume PDF

Drop `resume.pdf` into `assets/` — the "Download full resume" button already links to `assets/resume.pdf`.

## Deploy

### Vercel (recommended)

```bash
npm i -g vercel   # install CLI if needed
vercel            # follow prompts — pick "daniel-schwartzman-portfolio" as project name
vercel --prod     # promote to production
```

Or connect via the Vercel dashboard: Import Project → GitHub repo → deploy. Vercel auto-detects static sites.

### Netlify

Drag and drop the `Danielportfolio/` folder onto [netlify.com/drop](https://app.netlify.com/drop).

### GitHub Pages

```bash
git init && git add . && git commit -m "initial"
gh repo create daniel-schwartzman-portfolio --public --source=. --push
# then enable Pages in repo Settings → Pages → Deploy from branch (main / root)
```
