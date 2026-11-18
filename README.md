# PartCheck

Upload a photo of a car spare part and get a trust score, red flags, a rupee price verdict, genuine alternatives and a complaint report.

## Run it

Needs Node.js 18 or newer. No packages to install.

1. Put these four files in one folder: `server.js`, `index.html`, `package.json`, `README.md`.
2. Create a file named `.env` in the same folder:
   ```
   ANTHROPIC_API_KEY=your-key-here
   ```
   (Get a key at https://console.anthropic.com.)
3. Start it:
   ```
   node server.js
   ```
4. Open http://localhost:8080 (the server uses the `PORT` environment variable if set, otherwise 8080).

## Notes

- Photos are shrunk in the browser to 1600 px before upload.
- Reviews and dealers are optional JSON lists. Without them the app returns no review summary and no dealer list.
- The AI model can be changed with `MODEL=...` in `.env`.
- The API key stays on the server and is never sent to the browser.
- To deploy (Render, Railway, etc.), set `ANTHROPIC_API_KEY` as an environment variable. The host sets `PORT` for you.
- For the hackathon demo: the result is a risk estimate from the photo, not proof of authenticity.
