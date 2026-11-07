# Yoni's Apps

A static site of small personal web apps, served with GitHub Pages. No build step.

## Structure

```
index.html              hub page that links to every app
daily-memory/index.html Daily Memory: spaced-repetition flip cards
.nojekyll               tells GitHub Pages to serve the files as-is
```

Each app is a single self-contained HTML file in its own folder, so it also opens straight from disk.

## Adding an app

1. Create `<app-name>/index.html`.
2. Add a card for it in the root `index.html` (copy the Daily Memory card).

## Publishing

In the GitHub repo: **Settings → Pages → Build and deployment → Deploy from a branch → `main` / `/ (root)`**.
The site is then at `https://yehonatanmizrachi.github.io/yoni-apps/`.

## Apps

### Daily Memory

Flip cards with spaced repetition (simplified SM-2: Forgot / Hard / Easy) for words and terms in Hebrew and English.

- Add cards on the **Add** screen: term (required), meaning, category, and optionally example, origin and tags. The category stays filled in, so you can add several words to one category in a row.
- Each card has one optional **category** (for example "English words"). Review and Library can be filtered by category, and a category can be renamed (or merged into another) from the Library.
- You can also paste cards from a Claude chat under **Paste cards from Claude**: `term` is required; `meaning`, `example`, `origin`, `category` and `tags` are optional. A single object, an array, or a full backup `{ "cards": [...] }` all work. **Copy prompt for Claude** copies ready-made instructions for the chat, including your current categories.
- **Read aloud:** English terms get a speaker button on the card (front and back), next to an English example sentence, and in the Library. Press S in Review to hear the current term. It uses the browser's built-in voices, so it works offline.
- **Archive** cards you've finished learning: from the back of a card in Review ("I know this — archive it", or press A) or from the archive button in the Library. Archived cards leave Review and the due count but keep their history. Find them under **Library → Archive**, where **Restore** puts a card back into Review, due today. Archiving and restoring can be undone from the message that pops up.
- Cards are stored in `localStorage` under `dailyMemory.v1`. Use **Library → Export** for backups (`daily-memory-YYYY-MM-DD.json`) and **Restore** to load one (replace or merge by id).
- Keyboard: Space flips the card; 1 / 2 / 3 rate it.
