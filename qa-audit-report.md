# QA Audit Report — Cynbit Website

## 1. Executive summary

A focused manual quality audit was performed on the Cynbit website (`https://www.cynbit.in`) using desktop Chrome and Chrome DevTools mobile device emulation. The checks covered navigation, basic contact-form validation, responsive behaviour, keyboard navigation, HTTP-to-HTTPS redirection, and a Lighthouse audit of the Services page.

The recorded Lighthouse scores for the **Services page in mobile mode** were:

| Category | Score |
|---|---:|
| Performance | 60/100 |
| Accessibility | 90/100 |
| Best Practices | 77/100 |
| SEO | 100/100 |

The clearest measured improvement area is loading/rendering performance: LCP was 5.7 s, Speed Index 5.5 s and TBT 530 ms in the recorded run. Manual checks passed for the tested mobile menu, scrolling, keyboard navigation and form validation. No reproducible functional defect has been confirmed from the evidence collected.

## 2. Scope

### Included
- Desktop navigation visibility.
- Mobile page loading, hamburger menu and vertical scrolling.
- Responsive layouts at desktop (1920×1080), laptop (1366×768), tablet (768×1024) and mobile (390×844), by visual inspection.
- Keyboard navigation using Tab, Enter and Shift+Tab, including visible focus indication.
- Contact form empty submission and invalid email validation.
- HTTP-to-HTTPS redirection.
- Lighthouse results for `https://www.cynbit.in/services` in mobile mode.

### Not included
- Source-code or server configuration review.
- Penetration testing or vulnerability scanning.
- Exhaustive browser/device compatibility testing.
- Full WCAG conformance assessment or assistive-technology testing.
- Valid contact-form submission to the business.
- Verification of all pages and all form workflows.

## 3. Test environment

| Item | Recorded environment |
|---|---|
| Browser | Google Chrome (version not recorded) |
| Platform | Desktop/laptop; Windows environment |
| Responsive method | Chrome DevTools device emulation |
| Viewports visually inspected | 1920×1080, 1366×768, 768×1024, 390×844 |
| Lighthouse target | `https://www.cynbit.in/services` |
| Lighthouse mode | Mobile |
| Audit date | 4 November 2026 |

## 4. Methodology

1. Opened the public website in Chrome and inspected the visible desktop navigation.
2. Used Chrome DevTools device emulation to inspect the mobile layout and navigation.
3. Performed basic keyboard-only navigation checks.
4. Tested contact-form validation using empty fields and an invalid email address. A valid message was not submitted.
5. Entered the HTTP website address and verified that the browser navigated to the HTTPS version.
6. Ran Lighthouse for the Services page in mobile mode and recorded the displayed scores and metrics.
7. Reviewed the Lighthouse audit sections that were visible. The Best Practices score was 77/100; 11 passed and 2 not-applicable checks were reported. No failed audit item was identified in the sections inspected, so the underlying score deductions remain unconfirmed.

## 5. Test results

### 5.1 Manual functional and usability checks

| Area | Test | Result |
|---|---|---|
| Desktop navigation | Home and other navigation links visible | Pass |
| Mobile loading | Website displayed in mobile emulation | Pass |
| Mobile navigation | Hamburger menu opened | Pass |
| Mobile scrolling | Scrolled to page bottom/footer | Pass |
| Responsive layout | Visual inspection at four viewports | No obvious layout issue observed |
| Horizontal overflow | Mobile page inspection | No horizontal overflow observed |
| Keyboard | Tab moved through interactive elements | Pass |
| Keyboard | Enter activated focused navigation links | Pass |
| Keyboard | Visible focus outline appeared | Pass |
| Contact form | Empty submission displayed validation errors | Pass |
| Contact form | Invalid email was rejected | Pass |
| Contact form | Fields accepted normal input | Pass |
| Security transport | HTTP address redirected to HTTPS | Pass |

**Desktop hamburger clarification:** The desktop header displayed the standard navigation links (Home and other options). No separate desktop hamburger icon was visible. This is not recorded as a defect because a hamburger menu is not necessarily expected at desktop widths. The mobile hamburger menu was present and opened successfully.

### 5.2 Lighthouse results — Services page, mobile

| Metric | Result | Interpretation |
|---|---:|---|
| Performance | 60/100 | Needs improvement |
| Accessibility | 90/100 | Good score; not proof of WCAG conformance |
| Best Practices | 77/100 | Below recommended target; cause not identified |
| SEO | 100/100 | Strong result in this run |
| First Contentful Paint (FCP) | 1.8 s | At the good threshold |
| Largest Contentful Paint (LCP) | 5.7 s | Poor; target is 2.5 s or less |
| Speed Index | 5.5 s | Needs improvement |
| Total Blocking Time (TBT) | 530 ms | Needs improvement |
| Cumulative Layout Shift (CLS) | 0.013 | Good |

### 5.3 Additional Lighthouse diagnostics recorded

- Render-blocking resource estimated savings: approximately 720 ms.
- JavaScript execution time: approximately 1.6 s.
- Main-thread work: approximately 4.4 s.
- Long tasks: 8.
- Estimated unused JavaScript savings: approximately 113 KiB (including third-party and first-party scripts).
- The LCP element shown was the hero heading “Built for Scale, Designed for Performance.”
- The LCP breakdown showed approximately 50 ms TTFB and approximately 2,600 ms element render delay.
- Google Fonts appeared in the dependency chain; one font-related dependency was approximately 2,895 ms.

These are Lighthouse diagnostics and estimates from one run. They suggest areas to investigate but do not establish the exact source-code root cause.

### 5.4 Best Practices audit details

- 11 passed audits were displayed.
- 2 checks were marked not applicable: HTTP-to-HTTPS redirect audit and JavaScript library detection.
- The manual HTTP-to-HTTPS test was separately successful.
- No failed audit entries were visible in the sections reviewed. The reason for the 77/100 score was therefore not confirmed.

## 6. Defect summary

No reproducible functional defect was confirmed during the checks recorded in this report. The main actionable findings are performance improvements and follow-up investigation of the Best Practices score. See `bug-and-issue-log.csv`.

## 7. Limitations

- Lighthouse scores and timings can vary between runs due to network, device and browser conditions.
- Only the Services page Lighthouse report was recorded; these results must not be treated as site-wide measurements.
- Visual responsive checks do not replace automated viewport testing.
- Keyboard checks covered basic navigation only; they do not establish full accessibility compliance.
- No valid contact-form submission was made, so successful delivery and backend processing were not verified.
- The exact Chrome version and detailed test timestamps were not recorded.
