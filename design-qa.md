# Design QA

- Source visual truth path: `/Users/zhangxiaohu/Documents/Codex/2026-09-28/wei/work/cyber-chronicle-revised/map-of-powers-1536/image-1.png`
- Implementation: `http://127.0.0.1:4000/`
- Implementation screenshot: Codex in-app browser capture, tab 9, displayed in the task at `1536 x 1024` and `390 x 844`; the browser surface does not expose a filesystem export path.
- Full-view comparison evidence: `/Users/zhangxiaohu/Documents/Codex/2026-09-28/wei/work/notice-qa.html` rendered the selected design and the live notice side by side in the same browser capture.
- Viewports: desktop `1536 x 1024`; mobile `390 x 844`.
- State: public site-wide construction notice.

## Findings

No actionable P0, P1, or P2 differences remain.

- Fonts and typography: Songti SC/STSong retains the selected design's high-contrast editorial voice. The display headline is intentionally enlarged for the single-message holding state; metadata remains monospace and all copy wraps without clipping.
- Spacing and layout rhythm: the notice uses the source's wide editorial frame, fine rules, left-aligned story hierarchy, and map-led composition. Desktop and mobile each fit exactly within one viewport with no horizontal overflow.
- Colors and visual tokens: graphite black, paper white, cinnabar red, and brass are reused from the established site tokens. The background is darkened with solid opacity only; no gradient or glass treatment was added.
- Image quality and asset fidelity: the China-centered Image2 map remains the sole full-bleed visual, is sharp at both tested sizes, and preserves the source art direction. No placeholder image, custom SVG, or CSS-drawn substitute is present.
- Copy and content: the page states `网站制作中` explicitly, while `山河既动，史笔未落` and `正在修志` preserve the publication voice. No launch date, subscription promise, or unfinished article link is exposed.
- Interactions and accessibility: the holding page has no false CTA or dead navigation. The main landmark and heading hierarchy are present; unpublished post URLs return the same notice with HTTP 404. Browser console errors and warnings: none.

## Comparison History

### Pass 1

- [P2] The skip link appeared in the first narrow-screen capture even though the notice has no preceding navigation to skip.
  - Fix: removed the redundant link from the construction include.
  - Post-fix evidence: desktop and mobile captures begin directly with the brand masthead and contain zero visible links.
- [P2] The upper-right status read `乙巳卷 · 编修中`, which was atmospheric but not explicit enough for a public holding page.
  - Fix: changed the status to `网站制作中`.
  - Post-fix evidence: the message is visible in the upper-right corner at both tested viewports.

### Pass 2

- The side-by-side comparison confirms that the notice preserves the selected design's map asset, palette, typographic character, editorial rules, and restrained density while intentionally replacing article navigation with one clear construction message.
- Focused regions were checked at full size for the masthead, display headline, explanatory copy, progress strip, footer, China-centered map crop, and mobile text wrapping. No additional cropped comparison was needed because each region was legible in the full-size captures.

## Implementation Checklist

- [x] Site-wide construction flag added.
- [x] Existing homepage and article sources preserved.
- [x] Unfinished posts removed from generated routes and feed.
- [x] Search crawling paused through page metadata and `robots.txt`.
- [x] Desktop and mobile layouts visually verified.
- [x] Console, image loading, overflow, and direct post URL behavior checked.
- [x] Jekyll build and whitespace checks passed.

## Follow-up Polish

- P3: when the first editorial package is approved, remove the three per-post `published: false` flags and turn off `under_construction` in the same release.

final result: passed
