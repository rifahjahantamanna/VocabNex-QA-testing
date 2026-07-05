# Vocabnex — QA Testing Project

Manual QA testing project for [Vocabnex](https://vocab-nex.vercel.app/), a vocabulary learning web app with word tracking, flashcards, and a quiz feature.

## Objective

To evaluate the core functionality of Vocabnex through structured manual testing, identify defects, and document findings in a professional QA format — covering test planning, test case design, exploratory testing, and bug reporting.

## Scope

- **In scope:** User authentication (signup/login/logout), Add Word feature, Quiz flow, navigation between core pages, session handling.
- **Out of scope:** Performance/load testing, security penetration testing, cross-browser testing beyond Chrome.

## Approach

1. Exploratory testing session to understand actual app behavior (particularly around undocumented spaced-repetition logic)
2. Manual scripted test case design and execution
3. Defect logging with severity/priority classification
4. Summary reporting

## Deliverable

📄 [`Vocabnex_QA_Test_Plan.xlsx`](./Vocabnex_QA_Test_Plan.xlsx) — contains:
- **Test Plan** — scope, approach, environment, tools
- **Test Cases** — 25 test cases across Auth, Add Word, Quiz, and Navigation modules
- **Bug Log** — 9 defects logged with steps to reproduce, severity, and priority
- **Summary Report** — auto-calculated test execution metrics and key findings

## Key Findings

Testing surfaced 9 defects ranging from Low to High severity, including:

- **Data integrity:** No validation prevents invalid/non-dictionary words or duplicates from being added — these later appear as real quiz questions, directly affecting the core learning feature.
- **Scoring integrity (High):** Rapidly clicking "Next" during a quiz skips remaining questions but still generates a final score, producing an inaccurate result.
- **Inconsistent auth guarding:** Accessing protected routes while logged out results in a 404 on one page and an infinite loading state on another — neither redirects to login.
- **Missing error handling:** No fallback UI when the third-party quiz-generation API fails, leaving users with a blank screen.
- **Feature gap:** No observable spaced-repetition logic despite the app's core concept implying adaptive review.

No critical security issues were found in authentication or session handling.

## Tools Used

Excel (test design & tracking), Chrome DevTools (console inspection), manual exploratory testing techniques (boundary testing, negative testing).

## Author

Rifah Jahan Tamanna — QA enthusiast, testing real-world applications to build practical manual testing skills.