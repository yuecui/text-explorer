# Text Explorer update

This version keeps the existing floating search-results panel and adds:

- Collapsible result groups for **All Fiction** (grouped by `<div type="work">`).
- Collapsible result groups for **All Nonfiction** (grouped by `<teiSubTitle>` sections).
- Relative frequency across books/works, shown as occurrences per 10,000 words. The raw match count is shown in parentheses.
- An interactive frequency trend for each individual work, divided into 20 equal word-position segments.
- The same interactive frequency trend for individual-text searches.
- Clicking a corpus frequency row opens that work's result group.
- Clicking the trend graph jumps to the nearest occurrence in the text.
- The floating result window remains draggable, now using its header as the drag handle so result/chart interactions do not accidentally drag the panel.

Search matching intentionally preserves the existing behavior: a search for `friend` also matches words beginning with `friend`, such as `friendly` and `friendship`.

## Follow-up interaction/mobile fixes
- Clicking a frequency trend now opens the matching work (for corpus searches), scrolls the floating result panel to the nearest result, and highlights that result row.
- The selected result row uses a yellow background so it remains visually distinct.
- On mobile, the text selector is aligned with the other search controls and uses a smaller font/height.

## Mobile robustness update
- Corrected `FolderBase` for the current GitHub Pages layout to `./teiEncode/`.
- Search panel now appears immediately with a loading state before large-corpus processing.
- Added search-run cancellation so a newer search cannot be overwritten by an older pending search.
- Added XML-load cancellation so quickly changing works cannot display a stale fetch response.
- Corpus result rows are rendered lazily and in animation-frame batches instead of creating every result row at once.
- Trend clicks force-render only the needed work, then synchronize and highlight the exact result row.
- Disabled touch dragging of the floating panel on phones to avoid gesture conflicts with scrolling/tapping.
- Added viewport clamping and mobile viewport-height handling.
- Reduced mobile search-control sizes and aligned the selector/input/buttons.
- Mobile jumps use immediate scrolling to reduce simultaneous animation load in Safari.
