# Publications Formatting Guide

This guide explains how to format your publications to display in the beautiful format shown on the publications page.

## Folder Structure

- **Publication files**: `_publications/YYYY-MM-DD-publication-name.md`
- **Publication images**: `images/publications/`

## Creating a Publication

1. Create a new markdown file in the `_publications/` folder with the naming convention:
   ```
   YYYY-MM-DD-publication-name.md
   ```
   Example: `2025-01-01-chartgemma.md`

2. Use the following template for your publication:

```yaml
---
title: "Your Publication Title"
collection: publications
permalink: /publication/YYYY-MM-DD-publication-name
excerpt: 'Brief description of your publication.'
date: YYYY-MM-DD
venue: 'Conference or Journal Name'
authors: 'Author1, Author2, Author3'
paperurl: 'https://link-to-pdf-or-arxiv'
bibtex: 'https://link-to-bibtex-file'  # Optional
slides: 'https://link-to-slides'  # Optional
code: 'https://link-to-code'  # Optional
header:
  teaser: image-filename.png  # Name of image in images/publications/
citation: 'Full citation text'
---

Your publication abstract or description here.

[Download paper here](link-to-paper)

Recommended citation: Full citation text.
```

## Required Fields

- `title`: The publication title
- `collection: publications`: Must be set to "publications"
- `permalink`: URL path for the publication page
- `date`: Publication date (YYYY-MM-DD format)
- `venue`: Conference or journal name
- `authors`: List of authors (comma-separated)
- `paperurl`: Link to PDF or arXiv page

## Optional Fields

- `bibtex`: Link to BibTeX file
- `slides`: Link to presentation slides
- `code`: Link to code repository
- `header.teaser`: Image filename (place image in `images/publications/`)
- `excerpt`: Brief description
- `citation`: Full citation text

## Adding Images

1. Place your publication thumbnail image in `images/publications/`
2. Name the image file (e.g., `chartgemma.png`)
3. Reference it in the publication markdown:
   ```yaml
   header:
     teaser: chartgemma.png
   ```

**Image Recommendations:**
- Size: 200x120 pixels (or similar aspect ratio)
- Format: PNG, JPG, or WebP
- Content: A figure from the paper, diagram, or visual summary

## Button Colors

The publication template automatically creates colored buttons:
- **PDF**: Green button
- **BibTex**: Red/brown button
- **Slides**: Light blue button
- **Code**: Primary color button

## Example Publication

See `_publications/2025-01-01-chartgemma.md` for a complete example.

## Display Order

Publications are displayed in reverse chronological order (newest first) on the publications page.

## Converting Existing Publications

If you have publications listed in your `about.md` page, you can convert them to this format by:

1. Creating a markdown file in `_publications/` for each publication
2. Adding the appropriate metadata fields
3. Creating/adding thumbnail images to `images/publications/`
4. The publications will automatically appear on the publications page

