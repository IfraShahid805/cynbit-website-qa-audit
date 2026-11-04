# Cynbit Website Quality Assurance Audit

**Assessment:** QA Testing Intern – Website Quality Audit  
**Website:** https://www.cynbit.in  
**Audit date:** 4 November 2026  
**Status:** Manual checks and one Lighthouse run documented; findings are limited to the evidence collected.

## Repository contents

- `reports/qa-audit-report.md` — scope, methodology, environment, results and limitations.
- `reports/bug-and-issue-log.csv` — observed issues and items requiring further investigation.
- `reports/improvement-recommendations.md` — prioritised recommendations.
- `reports/test-cases.csv` — executed manual test cases and outcomes.
- `test-evidence/README.md` — instructions for adding original screenshots.

## How to review

Start with `reports/qa-audit-report.md`, then review the issue log and recommendations.

## Evidence and limitations

The report is based on manual browser checks and the Lighthouse results recorded during the assessment. No source-code review, automated regression suite, penetration test, or exhaustive WCAG audit was performed. Lighthouse metrics apply specifically to the **Services page in mobile mode** and should not be generalised to every page or device.

No screenshots are included in this package because original evidence images were not available to attach when the files were prepared. Add your own unaltered screenshots to `test-evidence/` and reference them in the report before submission.
