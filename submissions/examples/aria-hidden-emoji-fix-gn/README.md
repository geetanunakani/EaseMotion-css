# Fix: aria-hidden on Decorative Emoji (#2769)

1. **What's the bug?** The lightbulb emoji (💡) used as a decorative icon in `docs/index.html` lacked an `aria-hidden` attribute, causing screen readers to announce it as part of the content.
2. **The fix:** Added `aria-hidden="true"` to the `<span class="docs-info-icon">` wrapping the emoji in `docs/index.html`:
```html
<span class="docs-info-icon" aria-hidden="true">💡</span>
```
3. **How is it tested?** `demo.html` shows the same pattern — screen readers will skip the emoji and only announce the meaningful text.
4. **Why is it useful?** Improves accessibility by preventing confusing announcements for visually impaired users, aligned with EaseMotion CSS's accessibility commitments.