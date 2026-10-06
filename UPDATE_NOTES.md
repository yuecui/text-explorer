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
