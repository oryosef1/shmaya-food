Pre-release readiness check:

1. **Site health** — Open index.html, verify all sections render correctly
2. **Images** — Verify all images load (no broken images)
3. **Links** — Test all external links:
   - Waze navigation link
   - WhatsApp link
   - Instagram link
   - Facebook link
4. **Responsive** — Check mobile and desktop viewports
5. **RTL** — Verify Hebrew text and RTL layout are correct
6. **Performance** — Check that images have `loading="lazy"`, no unnecessary resources
7. **Meta tags** — Verify Open Graph tags are present for social sharing
8. **TODO blockers** — Check TODO.md for any blocking items
9. **Credential scan** — Ensure no API keys, tokens, or secrets in code
10. **Debug statements** — Search for `console.log` or debug code

Report: READY TO SHIP or list blockers.
