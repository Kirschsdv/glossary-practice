# Gr9 Study Hub — History & EMS

A free, mobile-friendly bilingual study tool for Grade 9 learners covering **History** and **EMS** (Economic and Management Sciences). Built as a single HTML file — no installation, no login, no internet connection required once downloaded.

🔗 **Live site:** `https://YOUR-USERNAME.github.io/gr9-study-hub`

---

## Features

- **Tweetalige woordelys / Bilingual glossary** — Afrikaans primary, English secondary. Toggle between Afrikaans only, English only, or both.
- **4 quiz modes** — Multiple choice, Flashcards, Fill in the blank, Match columns
- **Progress tracking** — Sessions, best score, day streak, mastered terms, badges (saved in browser localStorage)
- **Exam-weighted** — Terms ranked by CAPS exam evidence (Must-know / High priority / Good to know)
- **Offline-ready** — Works without internet after first load
- **Mobile-first** — Designed for phones; works on any screen size

---

## Subjects

| Subject | Topics | Terms |
|---------|--------|-------|
| 📜 History | Rise of Nazism, WW2 Europe, WW2 Pacific, Nuclear Age, Cold War, History Skills | 55 |
| 💹 EMS | Economic Systems, Circular Flow, Journals & GL, Credit Transactions, Price Theory, Sectors, Exam Language | 96 |

---

## How to deploy (GitHub Pages)

### First time setup

1. **Fork or create** a new GitHub repository named `gr9-study-hub`
2. **Upload** the `index.html` file to the root of the repository
3. Go to **Settings → Pages**
4. Under **Source**, select **Deploy from a branch**
5. Choose branch: `main`, folder: `/ (root)`
6. Click **Save**
7. Wait ~60 seconds — your site will be live at `https://YOUR-USERNAME.github.io/gr9-study-hub`

### Updating the tool

1. Edit `index.html` locally
2. Go to your repository on GitHub
3. Click on `index.html` → click the pencil ✏️ icon → paste updated content → **Commit changes**
4. GitHub Pages redeploys automatically within ~30 seconds

### Using GitHub Desktop (easier for non-developers)

1. Download [GitHub Desktop](https://desktop.github.com)
2. Clone your repository locally
3. Replace `index.html` with your updated version
4. In GitHub Desktop: write a commit message (e.g. "Add Natural Sciences subject") → **Commit to main** → **Push origin**

---

## Adding a new subject

Use the prompt in `EXTEND_PROMPT.md` to generate a new subject with Claude. Paste the updated `index.html` back into the repository.

Subjects that work well with this tool's format:
- 🔬 Natural Sciences
- 🌍 Geography
- ❤️ Life Orientation
- ➗ Mathematics (formulas & definitions)
- 🇿🇦 Social Sciences

---

## File structure

```
gr9-study-hub/
├── index.html          ← The entire app (single file)
├── README.md           ← This file
├── EXTEND_PROMPT.md    ← Prompt to add new subjects with Claude
└── .gitignore          ← Keeps the repo clean
```

---

## Privacy

All progress data (streaks, mastered terms, badges) is stored in your **browser's localStorage** — it never leaves your device. No accounts, no tracking, no ads.

---

## Licence

Free to use, share, and modify for educational purposes.
