# Local AI Chatbot (HTML/JS)

A fully offline, rule-based chatbot that runs entirely in the browser. No API keys, no server, no build tools.

## Files (must all be in the repo root / `main` branch)

```
your-repo/
├── index.html
├── chatbot.js
└── intents.json
```

## Run locally

Don't just double-click `index.html` — most browsers block `fetch()` on local files.
Instead, from inside the folder, run:

```bash
python -m http.server
```

Then open: `http://localhost:8000`

## Publish on GitHub Pages

1. Push `index.html`, `chatbot.js`, and `intents.json` to the root of your repo on the `main` branch (not inside a subfolder).
2. Go to your repo on GitHub → **Settings** → **Pages**.
3. Under "Build and deployment" → Source: **Deploy from a branch**.
4. Branch: `main`, folder: `/ (root)` → **Save**.
5. Wait a minute, then visit:
   `https://<your-username>.github.io/<repo-name>/`

This `github.io` link is the live site. The normal `github.com/.../repo` page only shows your code, it does not run it.

## Customize

Edit `intents.json` to add your own topics — no JS changes required:

```json
{
  "tag": "weather",
  "patterns": ["what's the weather", "is it raining"],
  "responses": ["I can't check live weather since I run offline!"]
}
```

## Troubleshooting

If the page loads but shows a red status message instead of "Ready to chat!", it means `intents.json` couldn't be fetched. Common causes:
- Opened the file directly instead of using a local server / GitHub Pages
- `intents.json` is missing or in the wrong folder
- A typo in the filename
