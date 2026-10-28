# Correct & Translate: deploy guide

This folder is a complete website:

- `index.html`: the page your friends see
- `api/translate.js`: a small server function that calls Gemini using your secret key
- Hosting on Vercel's free plan, translation on Gemini's free tier

## 1. Get a free Gemini API key
1. Go to https://aistudio.google.com and sign in with a Google account.
2. Click **Get API key**, then create a key.
3. Copy it and keep it private. Never paste it into `index.html`.

## 2. Put the project on GitHub
1. Create a free account at https://github.com if you don't have one.
2. Create a new repository (any name, e.g. `translator`).
3. Upload the contents of this folder: `index.html`, the `api` folder, and this README. Keep the `api/translate.js` path exactly as it is.

## 3. Deploy on Vercel
1. Sign up at https://vercel.com using your GitHub account (free Hobby plan).
2. Click **Add New → Project** and import your repository.
3. Before clicking Deploy, open **Environment Variables** and add:
   - Name: `GEMINI_API_KEY`
   - Value: the key from step 1
4. Click **Deploy**. In about a minute you get a link like `https://translator-yourname.vercel.app`.
5. Send that link to your friends.

## Optional settings (Environment Variables)
- `GEMINI_MODEL`: defaults to `gemini-2.5-flash`. If Google retires that name or you want a different free model, set this to another model that has a free tier (check Google's pricing page).

## Good to know
- Free-tier limits apply (requests per minute and per day). When they run out, the page shows a friendly message and works again later.
- The function allows 10 requests per minute per visitor and 2,000 characters per text.
- On the free tier, Google may use the text sent to improve its products. Ask friends not to paste private information.
- Voice input and read-aloud use the visitor's own browser. They work best in Chrome, and Papiamento uses a Dutch voice and model as a stand-in.
- To change something after deploying, edit the file on GitHub. Vercel redeploys automatically.
