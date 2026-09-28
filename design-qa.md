# Design QA

- Source visual truth path: `/Users/zhangxiaohu/Documents/Codex/2026-09-28/wei/work/cyber-chronicle-revised/map-of-powers-1536/image-1.png`
- Implementation: `http://127.0.0.1:4000/`
- Implementation screenshot: Codex in-app browser capture, tab 4, displayed in the task at `1536 x 1024` and `390 x 844`; the browser surface does not expose a filesystem export path.
- Full-view comparison evidence: `/Users/zhangxiaohu/Documents/Codex/2026-09-28/wei/work/qa-comparison.html` rendered the source and the live `1536 x 1024` implementation side by side in the same browser capture.
- Viewports: desktop `1536 x 1024`; mobile `390 x 844`.
- State: homepage default state; article and about-page navigation also tested.

## Findings

No actionable P0, P1, or P2 differences remain.

- Fonts and typography: Songti SC/STSong provides the source's high-contrast editorial display voice; system sans and monospace fallbacks preserve readable body copy and metadata. Heading scale, wrapping, line height, and zero letter spacing remain coherent at both tested viewports.
- Spacing and layout rhythm: the desktop retains the three-column chronology/map/factions composition, strong section rules, a centered lead chapter, and a visible hint of `战局新报` in the first viewport. Mobile collapses to one column without clipping; measured `scrollWidth` and `clientWidth` were both `375` CSS pixels.
- Colors and visual tokens: graphite black, paper white, cinnabar red, jade green, and brass map closely to the source. Contrast remains strong, and no gradients or glass effects were introduced.
- Image quality and asset fidelity: the dedicated Image2 world-map asset is sharp at desktop and crops cleanly on mobile. The three dispatch images share the same serious archival technology direction; no CSS drawings, placeholder imagery, or custom SVG substitutes are present.
- Copy and content: the site consistently uses `赛博志` as the brand. `AI时代演义` is not visible copy. Labels, chapter language, editorial promise, and sample posts express the requested historical-epic treatment while preserving a clear fact/interpretation boundary.
- Interactions and accessibility: keyboard focus styles are present; landmark labels, headings, image alt text, skip link, responsive navigation, article CTA, post return path, and about-page link were verified. Browser console errors and warnings: none.

## Comparison History

### Pass 1

- [P2] The map was too tall, pushing `战局新报` completely below the desktop viewport.
  - Fix: changed the desktop map height to `clamp(360px, 29vw, 460px)` and reduced the tablet height.
  - Post-fix evidence: the `1536 x 1024` capture shows the full lead chapter and the next section heading.
- [P2] The homepage lead used the full post title, adding `开篇：` and drifting from the selected mock.
  - Fix: the lead now renders `short_title`, while the article page keeps the complete editorial title.
  - Post-fix evidence: the homepage reads `群雄逐鹿，算力定鼎`.
- [P3] Side-rail headings lacked the selected mock's cinnabar section bands.
  - Fix: added restrained dark-cinnabar heading surfaces and matching divider color.

### Pass 2

- Full-view side-by-side comparison found no remaining structural or visual P0/P1/P2 mismatch.
- Focused regions were inspected separately at full size for the masthead, map labels, lead title, sidebar taxonomy, dispatch thumbnails, article typography, and mobile footer. A second cropped comparison was unnecessary because each region was legible in the full-size source and implementation captures.
- The right rail intentionally uses numbered typographic taxonomy instead of invented iconography. This preserves the source hierarchy without introducing an unmatched icon set.

## Implementation Checklist

- [x] Brand and metadata updated to `赛博志`.
- [x] Selected map-led homepage implemented with responsive side rails.
- [x] Generated map and dispatch imagery placed in the page and articles.
- [x] Three seed chapters and editorial-method page added.
- [x] Desktop and mobile layouts visually verified.
- [x] Primary navigation and article flow tested.
- [x] Jekyll build and whitespace checks passed.

## Follow-up Polish

- P3: when the publication has more than five sourced reports, expand `本纪` into a filterable archive rather than lengthening the homepage rail.

final result: passed
