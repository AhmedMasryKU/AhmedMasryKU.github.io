# Troubleshooting Publications Page

If the publications page is not showing the new format, try the following:

## 1. Rebuild Jekyll

If you're running Jekyll locally:

```bash
# Stop the current Jekyll server (Ctrl+C)
# Then restart it:
bundle exec jekyll serve
# or
jekyll serve
```

**Important**: Jekyll needs to recompile the SCSS files. Simply refreshing the browser won't work - you need to restart Jekyll.

## 2. Clear Browser Cache

After rebuilding Jekyll:
- Hard refresh: `Ctrl+Shift+R` (Windows/Linux) or `Cmd+Shift+R` (Mac)
- Or clear your browser cache

## 3. Check GitHub Pages

If you're using GitHub Pages:
- Push your changes to GitHub
- Wait a few minutes for GitHub Pages to rebuild
- The rebuild usually takes 1-2 minutes

## 4. Verify Files Are in Place

Make sure these files exist:
- `_includes/archive-single-publication.html` ✓
- `_sass/_publications.scss` ✓
- `assets/css/main.scss` (should import publications) ✓
- `_pages/publications.md` (should use archive-single-publication.html) ✓

## 5. Check Publication Files

Your publication files in `_publications/` should have at least:
- `title`
- `collection: publications`
- `date`
- `venue`
- `paperurl`

Optional but recommended:
- `authors` (if missing, will use site author name)
- `header.teaser` (for thumbnail image)

## 6. Test with Example Publication

The file `_publications/2025-01-01-chartgemma.md` is a complete example. If this one doesn't display correctly, there might be a syntax error.

## 7. Check Browser Console

Open browser developer tools (F12) and check for:
- CSS errors
- JavaScript errors
- Missing image files

## 8. Verify SCSS Compilation

Check if `_site/assets/css/main.css` (or similar) contains `.publication__item` styles after building.

