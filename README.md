# For Papa ♥ — Birthday keepsake

A responsive, seven-page birthday website made with plain HTML, CSS and vanilla JavaScript. It includes your uploaded family photographs, an interactive gratitude deck, 50 flip cards, a typewriter letter, a checkable bucket list and a celebratory final page.

## Preview locally

No build step or package installation is needed. From this folder run:

```bash
python3 -m http.server 8000
```

Then open <http://localhost:8000>. (ES modules require a local web server; opening the HTML directly as a `file://` URL may not work.)

## Personalise the gift

Edit **`data/content.js`**. It is the central content file and includes:

- `fatherName`, `daughterName`, `birthday`
- Hero heading and supporting line
- `memories`: photo path, caption, optional date, and description
- `gratitude`: 15 editable appreciation messages
- `reasons`: 50 editable reasons (keep 50 entries to show all numbered cards)
- `letter`: the complete letter text
- `bucketList`: starting list of shared experiences
- `finalMessage`, `finalPhoto`
- `music` and `voiceNote` optional audio paths

The supplied images are in `assets/photos/`. Replace any image by putting your photo in that folder and updating its relative path in `data/content.js`. The captions are gentle general sentiments, not asserted dates or specific events; edit them to reflect your real memories. Dates are blank until you add them.

### Add optional audio

Place an audio file (for example `birthday-song.mp3`) in `assets/`, then set `music: "assets/birthday-song.mp3"`. Music starts only after Papa taps the visible music control. For a recorded message set `voiceNote: "assets/papa-message.mp3"`. Keep audio files reasonably compressed for mobile.

### Change names and birthday

Set `fatherName`, `daughterName` and `birthday` near the top of `data/content.js`. `fatherName` is currently “Papa” and the daughter’s name and birthday are intentionally left as editable placeholders.

## Pages

1. `index.html` — welcome / open the surprise
2. `journey.html` — photo timeline
3. `gratitude.html` — tap-to-flip gratitude cards
4. `reasons.html` — 50 interactive reasons
5. `letter.html` — typewriter letter
6. `bucket-list.html` — persistent checkboxes and custom entries
7. `final.html` — final message, voice-note player and celebration

Each page is a real HTML file, so it works on GitHub Pages without SPA routing or rewrite rules. Links and asset paths are relative.

## Deploy to GitHub Pages (free)

1. Create a new **public** GitHub repository, for example `birthday-for-papa`.
2. In this project folder, run:

   ```bash
   git init
   git add .
   git commit -m "Create Papa birthday keepsake"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/birthday-for-papa.git
   git push -u origin main
   ```

3. In the repository go to **Settings → Pages** and choose **GitHub Actions** as the build/deployment source.
4. The included `.github/workflows/deploy.yml` deploys the project on every push to `main`.
5. Open **Actions** and wait for “Deploy birthday keepsake to GitHub Pages” to finish successfully. The live URL will be shown in the workflow and usually looks like `https://YOUR-USERNAME.github.io/birthday-for-papa/`.

GitHub Pages provides HTTPS. This project uses no backend, API keys or paid services. Google Fonts are an optional external font enhancement; system serif/sans fallbacks are included.

## Accessibility and performance

- Responsive layouts for phone, tablet and desktop.
- Reduced-motion preference is respected.
- Images use lazy loading outside the opening view.
- Music is off by default and never autoplays.
- Cards are real buttons and support keyboard activation.
- Photo fallback keeps the layout stable if a file is missing.
- Bucket-list checkmarks are saved in local browser storage on that device.

## Before sharing

- Replace `Your little girl` with your name.
- Add Papa’s birthday date if desired.
- Review every caption and the letter so they sound like you.
- Add an optional voice note or favourite song.
- Deploy, then test the published URL on a phone.
