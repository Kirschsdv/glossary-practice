# Prompt: Add a New Subject to Gr9 Study Hub

Copy everything below this line and paste it into a new Claude conversation.
Then attach or paste your `index.html` at the bottom.

---

I have a single-file HTML study tool (`index.html`) that I'll paste below. It supports multiple subjects, each with a Glossary, Quiz, and Study Guide. I need you to extend it by adding **[SUBJECT NAME]** as a new subject.

**The tool's structure — read this before touching anything:**

Each subject needs:
1. A subject pill button in the header (`subj-pills` div)
2. A subject container div (`<div class="subject" id="subj-[id]">`) containing three page divs: `[id]-page-glossary`, `[id]-page-quiz`, `[id]-page-guide`
3. A colour pair in `:root` CSS — `--c[n]` and `--c[n]-bg`, `--c[n]-bd` (follow the existing `--c1` for History and `--c2` for EMS)
4. A terms data array (e.g. `const [PREFIX]TERMS = [...]`)
5. A sections/topics array if the subject has multiple topics
6. Glossary build function using **DOM methods only** (no innerHTML string concatenation — this causes JS syntax errors with Afrikaans apostrophes like `'n`)
7. Quiz functions (all 4 modes: multiple choice, flashcard, fill-in-blank, match columns) mirroring the existing pattern
8. `localStorage` save/load for progress, streaks, badges

**Critical rules — do not break these:**
- **Never use `innerHTML` string concatenation to build glossary cards.** Always use `createElement` + `appendChild` + `textContent`. The Afrikaans `'n` apostrophe breaks JS strings.
- **Never use `onclick="..."` attribute strings on dynamically created elements.** Use `addEventListener('click', ...)` instead.
- All JS alert/string literals containing Afrikaans text must use **double quotes** or escape apostrophes — `'n` inside a single-quoted string crashes the whole script.
- The language toggle (`setLang`) is global — your new subject's glossary cards must use `gcard-af` (primary, large) and `gcard-en` (secondary, small) class names so the existing CSS body-class toggle works automatically.
- Afrikaans is the **primary language** — `gcard-af` (Afrikaans term) appears first/large, `gcard-en` (English term) appears second/small. Definition columns: `def-col af` first, `def-col en` second.
- The `switchSubject` function already handles page switching — just add your subject pill and container, then register it.
- Run a JS syntax check mentally before finishing: extract the `<script>` block and verify no unclosed strings.

**Term data format — History example (use when subject has clear exam weighting):**
```js
const HTERMS = [
  {
    tab: 'topicId',       // matches a section id
    p: 'p1',             // 'p1' = must-know, 'p2' = high priority, 'p3' = good to know
    e: 'English term',
    a: 'Afrikaanse term',
    why: 'Why this priority: exam evidence / CAPS reference',
    de: 'Full English definition.',
    da: "Volledige Afrikaanse definisie met 'n korrekte apostrof."
  },
]
```

**EMS term format (use when terms are more evenly weighted):**
```js
const ETERMS = [
  {
    t: 'Topic Name',
    tAf: 'Onderwerpnaam',
    en: 'English term',
    af: 'Afrikaanse term',
    dEn: 'English definition.',
    dAf: "Afrikaanse definisie met 'n korrekte apostrof.",
    key: true,    // true = ★ Must-know
    exam: true    // true = 📋 Exam term
  },
]
```

**What I need added:**

- Subject: **[e.g. Natural Sciences / Geography / Life Orientation]**
- Grade: **[e.g. Grade 9]**
- Terms covered: **[e.g. Term 1 and Term 2]**
- Topics/Chapters: **[list them]**
- Subject colour: **[e.g. deep blue / forest green / purple]**
- Subject icon emoji: **[e.g. 🔬 / 🌍 / ❤️]**
- Subject id (short, lowercase, no spaces): **[e.g. sci / geo / lo]**
- Term list: **[paste your terms, or say "generate from CAPS" and describe the topics]**
- Study Guide: **[paste exam format details, or say "generate standard Gr9 CAPS guide for [subject]"]**

**Here is the current `index.html`:**

```html
[PASTE YOUR FULL index.html HERE]
```

**Output:** Return the complete updated `index.html` with the new subject fully integrated. Do not truncate. Verify JS syntax before returning.

---

## Tips

- For **terms**, paste a list, a photo of your textbook glossary, or say *"generate all CAPS Grade 9 [subject] terms for Term 1 and 2"*
- For the **Study Guide**, the most useful content is: exam paper structure (sections, marks, time), cognitive level weighting, and 5–7 exam tips specific to the subject
- If Claude truncates the output, follow up: *"Continue from where you stopped — output the remaining HTML starting from [last line you saw]"*
- After adding a subject, commit `index.html` to your GitHub repository — GitHub Pages redeploys within ~30 seconds
