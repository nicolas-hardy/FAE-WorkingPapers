# FAE Working Paper publication workflow

This folder documents the publication convention for the FAE Working Paper Series.

## Design principle

The public site remains a static HTML/CSS site. The automation layer is deliberately additive: it does not replace or redesign the current pages. Existing `index.html`, `en/index.html`, paper pages, `styles.css`, images, newsletter pages, and navigation remain the source of truth for presentation.

## Standard publication package

For a new FAE Working Paper No. `N`, the publication package uses:

- `FAE-WP-N-AuthorSlug-YEAR.pdf` — final PDF with institutional FAE cover prepended.
- `wp-N-cover.png` — image used in the website card and paper page.
- `paper-N.html` — Spanish shell, while title/abstract/paper-specific academic content remains in the original language unless explicitly requested otherwise.
- `en/paper-N.html` — English shell.
- `publication/wp-N.json` — structured metadata for reproducibility.

The homepage files `index.html` and `en/index.html` are updated by inserting a new card above the previous most recent Working Paper, preserving the existing markup and CSS classes.

## Publication procedure used by ChatGPT

1. Read the submitted paper and extract title, authors, affiliations, date, abstract, keywords and JEL codes only from the supplied source.
2. Duplicate the current institutional cover template and update Working Paper number, title, authors and date without changing the visual design.
3. Prepend the cover to the submitted PDF and export the first page as `wp-N-cover.png`.
4. Create `paper-N.html` and `en/paper-N.html` using the current paper-page markup.
5. Insert the new card in `index.html` and `en/index.html`, preserving all existing site structure and CSS.
6. Commit the PDF, PNG, HTML and metadata to GitHub.
7. Verify that all links resolve on GitHub Pages.

## Important

No automatic templating engine is used on the live site. This avoids visual regressions. The metadata exists to standardize future additions, while the visible site remains exactly in its current static form.
