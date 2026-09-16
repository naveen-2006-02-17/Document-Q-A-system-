# Document Q&A System

An intelligent, browser-based application that lets you upload documents and ask questions about their content in natural language — instead of manually scanning through the text yourself.

Built entirely with **HTML, CSS, and JavaScript**. No backend, no build step, no dependencies to install — just open the file in a browser.

## Features

- **Multi-document upload** — add `.txt`, `.md`, or `.pdf` files (PDF text is extracted client-side via `pdf.js`)
- **Natural language Q&A** — ask a question in plain English and get the most relevant passages pulled directly from your documents
- **Keyword-weighted relevance ranking** — matches are scored using a lightweight TF‑IDF‑style algorithm, so rarer/more specific keywords count more than common ones
- **Confidence indicator** — each answer passage shows a relevance bar and label (strong / possible / weak match)
- **Search scope control** — query a single document or all uploaded documents at once
- **Highlighted matches** — matched keywords are highlighted inline in the returned passage
- **Document reader** — click any uploaded document to view its full text in a modal
- **Session export** — download the full Q&A conversation as a Markdown file
- **Sample documents** — try the system instantly with two built-in sample texts, no upload required
- **Dark mode** — toggle between light and dark themes, with your preference remembered
- **Fully client-side** — all processing happens in your browser; no documents are uploaded to a server

## How it works

1. **Upload** one or more documents from the sidebar (or click "Try sample documents").
2. Each document is split into sentences and tokenized.
3. When you **ask a question**, its keywords are compared against every sentence in the selected scope. Matches are scored using an inverse-document-frequency-style weighting, so distinctive keywords contribute more than generic ones.
4. The top-matching, non-overlapping passages are returned, each labeled with its source document and a confidence indicator.

This is a **retrieval-based** Q&A system — it finds and returns the most relevant existing sentences from your text rather than generating new answers, so every answer is traceable directly back to the source document.

## Getting started

No installation required.

```bash
git clone https://github.com/naveen-2006-02-17/document-qa-system.git
cd document-qa-system
open document-qa-system.html   # or just double-click the file
```

PDF parsing loads `pdf.js` from a CDN on first use, so an internet connection is needed for PDF uploads specifically; `.txt` and `.md` uploads and all Q&A functionality work fully offline.

## Project structure

```
document-qa-system/
└── document-qa-system.html   # Entire application — markup, styles, and logic in one file
```

## Tech stack

- HTML5
- CSS3 (custom properties for theming, no framework)
- Vanilla JavaScript (no build tools, no external JS frameworks)
- [pdf.js](https://mozilla.github.io/pdf.js/) (loaded via CDN, for PDF text extraction only)

## Limitations

- Answers are extracted, relevant sentences — not generated summaries or explanations
- Scanned/image-only PDFs with no embedded text layer cannot be read
- Relevance ranking is keyword-based, not a semantic/embedding-based model

## Author

**Naveen Kumar G**
B.Tech, AI & Data Science — Mailam Engineering College
[GitHub](https://github.com/naveen-2006-02-17) · [LinkedIn](https://linkedin.com/in/g-naveen-kumar-61733729a)

## License

This project is available for personal and academic use.
