# Chatmate English

A personal app for practising everyday English: you chat with old friends, people you half-know, and strangers you've just met. After each review the other person remembers what you talked about, and your relationship moves up a step (just met → half-familiar → close), so next time you pick up where you left off.

It's a web app (PWA). Once it's on your phone's home screen it works just like a regular app. It doesn't need a claude.ai subscription; it uses your own AI API key instead (Google Gemini has a free tier).

## Files

| File | Purpose |
|---|---|
| `index.html` | The whole app (UI + logic) |
| `manifest.webmanifest` | Lets the phone recognise it as an installable app |
| `sw.js` | Caches the app so it opens even without a connection |
| `icon-*.png`, `apple-touch-icon.png` | Home-screen icons |

## First-time setup

1. Open the app's URL (it needs to be hosted on https; see below).
2. Tap the gear icon at the top right and choose **Google Gemini**.
3. Go to <https://aistudio.google.com/apikey>, sign in with a Google account, tap **Create API key**, and paste the key into the app.
4. Tap "Save and test". Once it says the connection worked, you can start chatting.

The key is saved only in your phone's browser.

## Installing on your phone

- **iPhone**: open in Safari → Share button → **Add to Home Screen**
- **Android**: open in Chrome → menu → **Add to Home screen / Install app**

## Hosting

It's a static site; any free static hosting works:

- **GitHub Pages**: put this folder in a public repo, then Settings → Pages → Deploy from a branch
- **Netlify Drop**: <https://app.netlify.com/drop>, drag the `chatmate` folder in

## Data

Chats, memories and settings are all stored in the phone browser's localStorage. Clearing the browser data deletes them too.
