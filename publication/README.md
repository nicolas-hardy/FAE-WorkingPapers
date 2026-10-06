# FAE research publication workflows

This folder documents the conventions for the FAE Working Paper Series and the Latest Publications section.

## Design principle

The public site remains a static HTML/CSS site. The automation layer is deliberately additive: it does not replace or redesign the current pages. Existing `index.html`, `en/index.html`, paper pages, `styles.css`, images, newsletter pages, and navigation remain the source of truth for presentation.

## Working Paper package

For a new FAE Working Paper No. `N`, the publication package uses:

- `FAE-WP-N-AuthorSlug-YEAR.pdf` — final PDF with institutional FAE cover prepended.
- `wp-N-cover.png` — image used in the website card and paper page.
- `paper-N.html` — Spanish shell, while title/abstract/paper-specific academic content remains in the original language unless explicitly requested otherwise.
- `en/paper-N.html` — English shell.
- `publication/wp-N.json` — structured metadata for reproducibility.

The homepage files `index.html` and `en/index.html` are updated by inserting a new card above the previous most recent Working Paper, preserving the existing markup and CSS classes.

## Working Paper procedure used by ChatGPT

1. Read the submitted paper and extract title, authors, affiliations, date, abstract, keywords and JEL codes only from the supplied source.
2. Duplicate the current institutional cover template and update Working Paper number, title, authors and date without changing the visual design.
3. Prepend the cover to the submitted PDF and export the first page as `wp-N-cover.png`.
4. Create `paper-N.html` and `en/paper-N.html` using the current paper-page markup.
5. Insert the new card in `index.html` and `en/index.html`, preserving all existing site structure and CSS.
6. Commit the PDF, PNG, HTML and metadata to GitHub.
7. Verify that all links resolve on GitHub Pages.

## Latest Publications section

The public pages are `publications.html` and `en/publications.html`. This section is for journal publications rather than FAE Working Papers.

For each publication, ChatGPT should use the supplied paper, DOI, or official journal webpage as the source and extract only source-supported information. Each entry should contain:

- title;
- authors;
- journal;
- abstract;
- year and bibliographic details when available;
- DOI and/or official journal URL when available.

Structured metadata follows `publication/publication-template.json`. New publication records should be stored as `publication/article-YYYY-slug.json`.

When a new journal publication is provided, ChatGPT should:

1. read the paper or official journal/DOI source;
2. extract the bibliographic metadata and abstract without silently filling unsupported gaps;
3. create the structured metadata file;
4. add the article to `publications.html` and `en/publications.html` using the existing site design;
5. update the homepage Latest Publications teaser if appropriate;
6. preserve the original title and abstract language unless the user explicitly requests translation;
7. link to the official journal page or DOI when available.

## Important

No automatic templating engine is used on the live site. This avoids visual regressions. The metadata exists to standardize future additions, while the visible site remains in the current static form.
