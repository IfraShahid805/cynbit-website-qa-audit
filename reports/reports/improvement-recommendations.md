# Improvement Recommendations — Cynbit Website

Recommendations are prioritised by likely user impact and the available evidence. These are proposed actions, not claims that the underlying implementation has been inspected.

## Priority 1 — Improve Largest Contentful Paint

**Evidence:** Services-page mobile Lighthouse LCP was 5.7 s. The reported LCP element was the hero heading, with an element render delay of about 2,600 ms and TTFB around 50 ms in that run.

**Recommended actions**
- Profile the hero section in Chrome Performance and Lighthouse to identify styles, scripts, fonts or rendering work delaying the heading.
- Ensure critical above-the-fold CSS is delivered efficiently and defer non-critical styles where safe.
- Check whether font loading delays hero text rendering; consider reducing font weights, using efficient WOFF2 assets, `font-display: swap`, and preloading only the genuinely critical font.
- Re-run Lighthouse on the same URL, mobile mode and comparable conditions after each change.

## Priority 2 — Reduce render-blocking resources

**Evidence:** Lighthouse estimated approximately 720 ms savings from render-blocking requests.

**Recommended actions**
- Review the two first-party CSS resources and Google Fonts CSS identified by Lighthouse.
- Inline only small critical CSS where appropriate; load non-critical CSS without blocking initial rendering.
- Avoid adding preload hints indiscriminately; validate each change with a repeat audit.

## Priority 3 — Review JavaScript execution and unused code

**Evidence:** Lighthouse recorded about 1.6 s JavaScript execution, 4.4 s main-thread work, 8 long tasks and estimated unused JavaScript savings of about 113 KiB.

**Recommended actions**
- Use a coverage report and bundle analysis to identify unused first-party JavaScript.
- Remove or defer scripts that are not needed for the initial viewport.
- Review third-party tags, including Google Tag Manager, and load only required tags.
- Split large tasks and avoid expensive work during initial rendering.

## Priority 4 — Investigate Best Practices score

**Evidence:** Best Practices score was 77/100, while 11 audits passed and 2 were marked not applicable. No failed audit item was visible in the inspected sections.

**Recommended actions**
- Re-run Lighthouse and expand every flagged audit item, including diagnostics and any collapsed sections.
- Record the exact audit title, affected URL and evidence before assigning a defect.
- Do not infer the cause from the score alone.

## Priority 5 — Continue accessibility validation

**Evidence:** Lighthouse Accessibility score was 90/100. Manual Tab, Enter and visible-focus checks passed.

**Recommended actions**
- Inspect each form control for a persistent programmatic label, not only placeholder text.
- Check heading hierarchy, landmark structure, image alternative text, colour contrast and accessible names.
- Test with a screen reader and keyboard-only navigation across the full page.
- Review the exact Lighthouse Accessibility findings before logging any specific accessibility defect.

## Priority 6 — Expand regression coverage

- Repeat key flows on current Chrome, Firefox and Edge.
- Test the contact form with an approved test endpoint or authorised test data to verify successful submission and error handling.
- Add viewport checks around common breakpoints, not only the four sampled sizes.
- Capture screenshots and record browser version, URL, viewport and test date for reproducibility.

## Retest criteria

- Repeat the Services-page mobile Lighthouse audit under comparable conditions.
- Aim for LCP at or below 2.5 s, TBT at or below 200 ms, CLS at or below 0.1 and Speed Index at or below 3.4 s.
- Confirm that performance changes do not break navigation, form validation or responsive layouts.
