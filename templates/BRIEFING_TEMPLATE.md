# Daily briefing markup reference

Used by the daily update run. These blocks are copied from the live pages
(ai.html, dow.html, space.html, cyber.html). Match them exactly; do not add
classes, restyle, or restructure. Indentation matters to the update tooling:
items sit at 4 spaces, their inner elements at 6.

## Rules

- Window: trailing 7 days. Remove any item whose date, or range END date, is
  more than 7 days before today.
- Dates: `Oct 13`, ranges `Oct 7&ndash;8`, cross-month `Sept 30&ndash;Oct 7`.
  Verify against the source, not the headline.
- Entities: `&amp;` `&rsquo;` `&ldquo;` `&rdquo;` `&ndash;` `&mdash;` `&middot;`.
  Links use `target="_blank"`, separated by ` &middot; `.
- Say so when only secondary outlets report something or only a search summary
  was seen. Label rumors and analyst speculation as such.
- A section with nothing in the window gets exactly one empty item (below).
  Never mix an empty item with real items.

## Item

```html
    <div class="item">
      <div class="headline"><span class="date">Oct 13</span>Short factual headline</div>
      <p>Two to five sentences: what happened, key figures, caveats and disputed details.</p>
      <div class="src"><a href="https://example.com/a" target="_blank">Outlet A</a> &middot; <a href="https://example.com/b" target="_blank">Outlet B</a></div>
    </div>
```

## Empty item

```html
    <div class="item empty">
      <p>No significant new developments in the past week.</p>
    </div>
```

## Section (ai.html, space.html, cyber.html: `company`)

```html
  <section class="company anthropic" id="anthropic">
    <h2><span class="dot"></span>Section name</h2>
    <!-- items, or one empty item -->
  </section>
```

dow.html uses `<section class="cat afspace" id="afspace">` and adds
`<p class="sub">...</p>` under the `<h2>`.

## Header

```html
    <div class="meta">Compiled <strong>Thursday, October 15, 2026</strong> &middot; topic list</div>
    ...
    <div class="note">
      Static snapshot from public web search; does not auto-refresh. Window covered
      (e.g. Oct 8&ndash;15). Items older than seven days were removed. Sourcing limits.
    </div>
```

Footer: `compiled October 15, 2026` (update the date; keep the rest of the wording).
