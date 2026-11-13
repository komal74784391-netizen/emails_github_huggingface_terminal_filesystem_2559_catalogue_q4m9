# Bramblewick Bench Catalogue (source)

This repository holds the Markdown source for the Bramblewick Bench component
catalogue. Entries live in `content/catalog/`, one file per component.

`_data/modules.json` is consumed by the bench planner. It is generated from the
entries and must be regenerated whenever the catalogue content changes.

The site is built by a small static generator; no external dependencies are
required.
