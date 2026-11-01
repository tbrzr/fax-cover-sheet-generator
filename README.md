# fax-cover-sheet-generator

A free fax cover sheet maker that runs entirely in your browser. Fill in the fields, then print the sheet, save it as a PDF, or download a PDF with editable form fields.

Live version: https://harborprivacy.com/fax-cover-sheet-generator

It is maintained by [Harbor Privacy](https://harborprivacy.com), which also runs [Harbor Fax](https://fax.harborprivacy.com), a pay-per-fax service. The tool is free and does not require Harbor Fax.

## Privacy

Everything happens in the page's JavaScript. Nothing you type is uploaded, stored, or logged. You can check this in `index.html`. The only network requests are the page itself and its fonts. This copy has no analytics.

## Use it

Open `index.html` in a browser. No build step, no server, no dependencies to install.

```
git clone https://github.com/tbrzr/fax-cover-sheet-generator
cd fax-cover-sheet-generator
xdg-open index.html     # or open it in any browser
```

## What it does

- Live letter-size preview of the cover sheet.
- **Print or save as PDF** produces a flat one-page sheet through the browser's print dialog.
- **Download fillable PDF** builds a one-page PDF with 16 editable form fields (text fields and checkboxes), pre-filled with what you typed, using [pdf-lib](https://github.com/Hopding/pdf-lib).
- **Copy as text** copies a plain-text version.

## Limits

- The fillable PDF uses the built-in Helvetica font, so characters outside basic Latin (emoji, non-English scripts) are replaced with `?`.
- The confidentiality notice is generic text, not legal advice. Use your organization's wording if it has one.
- The fonts load from Google Fonts. Remove the `<link>` tags in `index.html` if you want zero third-party requests; the page falls back to system fonts.

## Relationship to the live page

The live page at harborprivacy.com is the canonical copy. This repo is the same code, with two differences: the analytics tag is removed, and the pdf-lib path is relative so the file works when opened directly. Fixes made on the live page are copied here.

## Third-party code

`vendor/pdf-lib-1.17.1.min.js` is [pdf-lib](https://github.com/Hopding/pdf-lib) 1.17.1 by Andrew Dillon, MIT licensed. Its license is in `vendor/pdf-lib-LICENSE.md`.

## Contributing

Issues and pull requests are welcome, for example layout fixes, other paper sizes, or field changes.

## License

MIT. See `LICENSE`.
