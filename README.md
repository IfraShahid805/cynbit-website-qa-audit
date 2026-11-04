# Cynbit Website Quality Assurance Audit

## Project Overview
This project presents a Quality Assurance (QA) audit of the Cynbit website, conducted as part of the QA Testing Intern assessment.

**Website:** https://www.cynbit.in  
**Testing Date:** 4 November 2026  
**Testing Type:** Manual Testing and Lighthouse Performance Audit  
**Browser:** Google Chrome

## Objectives
- Evaluate website functionality and navigation.
- Test responsive behaviour across desktop, tablet and mobile viewports.
- Verify basic form validation.
- Perform keyboard accessibility checks.
- Evaluate performance using Google Lighthouse.
- Identify improvement opportunities and provide recommendations.

## Testing Summary

| Testing Area | Result |
|---|---|
| Desktop Navigation | Passed |
| Mobile Navigation | Passed |
| Responsive Layout | No obvious issues observed |
| Contact Form Validation | Passed |
| Keyboard Navigation | Passed |
| HTTP to HTTPS Redirect | Passed |

## Lighthouse Results
*Services page — Mobile audit*

| Category | Score |
|---|---:|
| Performance | 60/100 |
| Accessibility | 90/100 |
| Best Practices | 77/100 |
| SEO | 100/100 |

### Key Performance Findings
- Largest Contentful Paint (LCP): 5.7 seconds
- Speed Index: 5.5 seconds
- Total Blocking Time (TBT): 530 ms
- Cumulative Layout Shift (CLS): 0.013

## Repository Structure
- reports/qa-audit-report.md — Detailed QA audit report.
- reports/bug-and-issue-log.csv — Findings and investigation log.
- reports/improvement-recommendations.md — Prioritised recommendations.
- reports/test-cases.csv — Manual test cases and results.
- test-evidence/ — Screenshots and supporting evidence.

## Tools Used
- Google Chrome
- Chrome Developer Tools
- Lighthouse
- GitHub

## Conclusion
The audit identified performance optimisation opportunities, particularly in Largest Contentful Paint, Speed Index and Total Blocking Time. The tested navigation, form validation and basic keyboard interactions worked as expected.

This assessment documents observed results and recommendations. It does not constitute a full security penetration test or complete WCAG compliance audit.

---
**Prepared as part of the Cynbit QA Testing Intern Assessment.**
