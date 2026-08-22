# Bible Study Quiz Help

## What this project is
This is a browser-based Bible study quiz app that runs from a single `index.html` file.
It is designed for local use (no server, no npm, no build tools).

The app reads your local Markdown chapter files from a selected folder, then creates a verse-based study quiz.

## Important content note
- Study questions in this project were generated with AI.
- Questions and answers may contain mistakes.
- The content has not been vetted or approved by a human reviewer.
- Use this project as a study aid, not as a final authority.

## How it works
1. You open `index.html` by double-clicking it.
2. You select the `md-files` folder using the folder picker.
3. The app finds all `.md` files and lists them.
4. You choose a chapter file and (optionally) a verse group.
5. The app parses question blocks from the markdown.
6. It builds a quiz with exactly one random question per verse.
7. You reveal each answer before moving to the next verse.

## Markdown format expected
Each question block should follow this pattern:

```markdown
### Proverbs 21:3

**Q7. Question text?**
**Answer:** Answer text.
**Verse:** Proverbs 21:3
```

Rules:
- Question numbers continue across the chapter.
- Verse groupings are based on the value after `**Verse:**`.
- The parser tolerates extra spacing, Windows/Unix line endings, and skips malformed entries.

## Main features
- Works offline from `file://`.
- Safe parsing with text-only rendering (no unsafe HTML injection).
- One-question-at-a-time verse quiz flow.
- Verse group dropdown (all verses or grouped ranges).
- Restart quiz from same chapter/group with fresh random picks.
- Return to start page from any view.

## Why folder selection is required
Browsers block automatic directory scanning for pages opened with `file://`.
That is why the app uses a folder picker and waits for you to click Upload.

## Troubleshooting
- If no files appear in the chapter dropdown:
  - Make sure you selected the folder that contains `.md` files.
  - Click Upload in the folder dialog after selecting the folder.
- If a file loads but quiz cannot start:
  - Verify the markdown contains `Q`, `Answer`, and `Verse` lines in each block.
- If warnings appear:
  - Some verses may not have exactly 3 valid questions; those with at least 1 valid question still work.

## File overview
- `index.html`: Entire app (UI, parser, quiz logic).
- `md-files/`: Study content markdown files.
- `AI-Prompt.txt`: Prompt template used to generate chapter questions.

## AI-Prompt.txt usage
`AI-Prompt.txt` is a reusable generation template that helps you create new chapter files in the exact format this app expects.

How to use it:
1. Open `AI-Prompt.txt`.
2. Replace BOOK CHAPTER with your target chapter, for example Proverbs 25.
3. Submit the prompt in your AI assistant.
4. Save the output markdown file in `md-files`.
5. Confirm question numbering is consecutive and each verse has 3 questions.

## Before publishing updates
- Test by opening `index.html` and running one full quiz.
- Confirm new markdown files appear and parse correctly.
- Keep question numbering consecutive in each chapter file.
