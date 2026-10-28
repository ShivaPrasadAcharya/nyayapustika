# Nyayapustika

A searchable PDF and plain-text catalogue for judicial orders and reference material.

**Website:** https://shivaprasadacharya.github.io/nyayapustika/

## Browse and search

- Five-column table: SN, folder name, file name, links, and remarks.
- Filename, folder, and remarks search; advanced filters, sorting, Nepali normalization, and next/previous match navigation.
- PDF previews with a direct-open/download fallback, TXT previews, text copying, and fullscreen controls.
- Floating buttons to go to the top and bottom.
- Rows per page: **100 (default), 150, 200, 250, 300, All**.
- Search covers catalogue fields, not document contents.

## PDF and TXT pairing

PDF and TXT files with the same filename stem share one table row. The PDF row provides **Open TXT**. Standalone TXT files remain visible in All files and Standalone TXT. Matching ignores extension case and normalizes Unicode names; matching files in the same folder take priority. Ambiguous TXT matches remain separate.

The summary counts show:

| Count | Meaning |
| --- | --- |
| PDF–TXT pairs | PDF files with a linked TXT companion |
| Total PDF files | Every PDF in the repository |
| Total text files | Every TXT, including paired and standalone TXT |
| Standalone PDF files | PDFs without a TXT companion |

## Mobile and clock verification

The entry screen uses the same configured mobile-number check as Adeshpustika. After entering that number, type the clock's current **HHMM** value without a colon. For example, **09:05 → 0905** and **18:30 → 1830**.

- The clock has hands and a 24-hour digital display, using **Asia/Kathmandu** time.
- The four-digit code changes every minute. If the minute changes while entering it, use the newly displayed code.
- Time is based on the visitor's device clock; keep the device time accurate.
- No SMS is sent. The mobile number and entered code are neither transmitted nor saved.
- As in Adeshpustika, a verified browser session lasts up to six hours. It can be reused when returning within one hour of the last recorded presence. Session storage contains timestamps only.
- This is a simulated, browser-side entry screen, **not secure authentication or proof of phone ownership**. The repository and document URLs remain public.

The configured mobile number, clock logic, and session settings are in the access-screen script inside `index.html`.

## Add files

1. Click **Add files** and sign in to GitHub with repository write access.
2. Upload PDF or UTF-8 TXT files and commit to `main`.
3. To link a text companion, use the same filename stem as its PDF.
4. After GitHub Pages finishes publishing, refresh the catalogue.

The page refreshes its file list from the repository on load. If GitHub's API is temporarily unavailable or rate-limited, the embedded saved catalogue remains usable. Other formats and this README are not listed as documents.

The original imported files use short stored paths to avoid filesystem filename-length limits; their full original names are preserved in the page's embedded metadata. When adding a companion to an imported PDF that has none, use the original filename shown in the catalogue with a `.txt` extension. Update the corresponding embedded metadata if you change an imported file's stored path.

## Project and publishing

- `index.html` contains the application, styles, favicon, saved file metadata, and verification screen.
- PDF and TXT files are stored in the repository.
- `README.md` documents the project and its operation.
- GitHub Pages publishes the `main` branch from the repository root.

To preview the page locally, run `python3 -m http.server 8000` in the repository and open http://localhost:8000/. An HTTP server is required for TXT preview requests.

Adapted from [Adeshpustika](https://github.com/ShivaPrasadAcharya/adeshpustika).

