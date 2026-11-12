# RLHF Book Course Materials

**Author:** Nathan Lambert. **Course:** [rlhfbook.com/course](https://rlhfbook.com/course). **Retrieved:** 2026-11-12.

Start with the [course summary](SUMMARY.md), then use the [lecture catalog](LECTURES.md) to open local PDFs, Markdown sources, and the corresponding online recordings.

## Included Material

- All 14 numbered lecture decks (0–13), in Markdown and PDF.
- Three Q&A decks, including the published corrections.
- Conversation 1 in Markdown and PDF; Conversation 2 as its supplied PDF.
- The Shoggoths bonus deck and the Cornell and SALA 2026 guest lectures.
- All 17 book chapters, appendices, and the chapter bibliography.
- The upstream companion code library and its documentation for the suggested exercises.
- A text snapshot of the course landing page, original license texts, and a file manifest with source URLs and checksums.

Videos remain linked to their original recordings. Other talks and external resources listed on the landing page are retained as links rather than copied. The downloaded texts and PDFs support local reading; this folder is a reading snapshot, not a configured course website build or a ready-to-run training environment.

## Layout

```text
rlhf-book-course/
├── README.md                 # Scope, provenance, and licenses
├── SUMMARY.md                # Course synthesis for the seminar
├── LECTURES.md               # Local slides, sources, and recording links
├── CITATION.bib              # Author's recommended web/arXiv citation
├── manifest.json             # Provenance and integrity metadata
└── source/
    ├── course-page.md        # Text extracted from the course landing page
    ├── LICENSE-CHAPTERS      # Original book-text license
    ├── LICENSE-CODE          # Original MIT license
    ├── README.md             # Original upstream repository README
    ├── book/chapters/        # Chapters, appendices, and bib.bib
    ├── code/                 # Original companion implementations
    └── teach/                # Lecture Markdown, bibliographies, and PDFs
```

Markdown sources preserve the original text and references. Standalone figure directories used to build the book and lecture sources are not duplicated; open the local slide PDFs for complete lecture visuals or the online book for chapter figures. The companion code's own small image directory is preserved with that library.

## Provenance

The upstream repository is [natolambert/rlhf-book](https://github.com/natolambert/rlhf-book). Text sources and companion code were downloaded from commit [`0be34d8ed8a66cd0b41d4f98123987e2526d05cd`](https://github.com/natolambert/rlhf-book/commit/0be34d8ed8a66cd0b41d4f98123987e2526d05cd) and checked against their Git blob hashes. Original upstream files remain unchanged.

The official slide PDFs were downloaded separately from the course website, except Conversation 2's PDF, which comes from the pinned repository. Website PDFs have retrieval dates and SHA-256 hashes; they are not asserted to have been built from the same source commit. The extracted landing page is also identified separately in [manifest.json](manifest.json).

The summary and navigation files are repository additions. No lecture recordings were watched or transcribed to create this summary; it draws on the published written material. The original landing-page snapshot preserves additional links and the author's published citation options.

## Attribution and Licenses

According to the [upstream README](source/README.md), `book/chapters/` is licensed under **CC BY-NC-SA 4.0**, while the remaining upstream material, including teaching sources and code, is under **MIT**. Both original license texts are included. Nathan Lambert retains the original attribution; third-party material retains its original notices.

The authored [summary](SUMMARY.md) is marked CC BY-NC-SA 4.0. These notices apply to this imported material and its adaptation, not to the repository as a whole. Cite the original course or book for academic use, and cite individual research papers when supporting experimental claims.

The companion code is provided as reference material. Follow its own [setup documentation](source/code/README.md) if experiments become part of the seminar; models, datasets, dependencies, and execution resources are not bundled here.
