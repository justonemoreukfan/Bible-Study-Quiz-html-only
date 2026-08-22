# Bible Study Quiz (KJV Markdown)

A single-file, offline Bible study quiz website that runs by double-clicking `index.html`.

No frameworks, no npm, no build tools, and no web server required.

## Important content note
- Study questions in this project were generated with AI.
- Questions and answers may contain mistakes.
- The content has not been vetted or approved by a human reviewer.
- Use this project as a study aid, not as a final authority.

## Features
- Loads local markdown files from a user-selected folder.
- Finds all `.md` chapter files and lists them in a dropdown.
- Parses verse-based study questions from markdown.
- Shows one random question per verse.
- Preserves verse order from the chapter file.
- One-question-at-a-time flow with answer reveal before next.
- Verse-group selector (for example: all verses, 1-10, 11-20).
- Restart quiz or choose another file without page reload.
- Works offline through `file://`.

## Project structure

```text
bible-quest/
  index.html
  AI-Prompt.txt
  HELP.md
  md-files/
    Proverbs21StudyQuestions.md
    Proverbs22StudyQuestions.md
    Proverbs23StudyQuestions.md
    ...
```

## Quick start
1. Clone or download this repository.
2. Open `index.html` by double-clicking it.
3. Click the folder picker and select `md-files`.
4. Click Upload in the browser dialog.
5. Select a chapter file and a verse group.
6. Click Start Quiz.

## Markdown format
The parser expects entries like:

```markdown
### Proverbs 21:3

**Q7. What is better than sacrifice according to Proverbs 21:3?**
**Answer:** To do justice and judgment.
**Verse:** Proverbs 21:3
```

Guidelines:
- Use exactly one chapter per file.
- Keep questions numbered consecutively in that chapter.
- Include `Question`, `Answer`, and `Verse` lines for each item.

## About AI-Prompt.txt
`AI-Prompt.txt` is the template prompt used to generate chapter study-question files in a consistent format.

How to use it:
1. Copy the full prompt text from `AI-Prompt.txt`.
2. Replace BOOK CHAPTER with a target chapter, for example Proverbs 24.
3. Send the prompt to your AI tool.
4. Save the generated markdown file into `md-files`.
5. Verify that the file has exactly 3 questions per verse and consecutive numbering before using it.

## Security and privacy notes
- The app runs entirely in your browser.
- Files are read locally from the folder you select.
- No network upload is required by the app.


## More help
See `HELP.md` for a full explanation of the app behavior and troubleshooting.
