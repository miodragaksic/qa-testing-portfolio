# YardRedesign — Manual QA Case Study

## Project overview

- **Product:** YardRedesign.com
- **Type:** AI-powered landscape redesign web application
- **Role:** Manual QA / Product Testing
- **Environment:** Production web app, FREE-user browser session (not logged in as administrator)
- **Testing:** Exploratory, functional, usability, negative, state/context and AI-behavior testing

## Objective

Evaluate image upload, chat context, AI text vs redesign behavior, repeated Send actions, validation, error handling, image-context changes and FREE quota boundaries.

## QA method

Each observation was compared with expected user behavior. When later evidence contradicted an earlier hypothesis, the conclusion was revised instead of forcing the original assumption.

## Findings

| ID | Area | Finding | Status |
|---|---|---|---|
| YR-001 | Chat UX | Input focus does not automatically return after AI response | UX observation |
| YR-002 | Image upload | Multiple-image selection/replacement is not sufficiently clear | Needs clarification |
| YR-003 | Request flow | Generation flow can appear before intent is clearly resolved | Needs retest |
| YR-004 | Image context | Current active image is not clearly communicated | UX issue |
| YR-005 | Before/After | Original image is not clearly exposed as a separately openable asset | Requirement clarification |
| YR-006 | Chat routing | Normal chat message can enter image-generation UI state before text response | Reproduced |
| YR-007 | Multi-image context | New image appears to replace previous active working image without explicit notice | UX / requirement issue |
| YR-008 | Image description | Similar image-description requests produced inconsistent behavior | Reproduced |
| YR-009 | FREE quota | “Please try again” can appear while quota prevents retry until reset | Reproduced |

## Positive tests

- Empty Send correctly returned **“Write a message or upload a photo.”**
- Rapid repeated Send did not create a duplicate message in the observed test; the second action reached empty-input validation.

## Evidence-driven conclusion

During image-context testing, an initial hypothesis was that a previous image had been deleted because of the displayed image count. A cleaner test showed that a visibly selected/uploaded image did not necessarily change the displayed `imgs` value. Therefore the counter alone was **not accepted as proof of deletion**.

This is an important QA practice: **new evidence changes the conclusion**.

## Documentation

- [Test Plan](test-plan.md)
- [Test Cases](test-cases.md)
- [YR-006 — Chat enters generation state](bug-reports/YR-006-chat-enters-generation-state.md)
- [YR-007 — Active image replacement](bug-reports/YR-007-active-image-replacement.md)
- [YR-008 — Inconsistent image description](bug-reports/YR-008-inconsistent-image-description.md)
- [YR-009 — Misleading FREE limit status](bug-reports/YR-009-misleading-free-limit-status.md)
- [Evidence directory](evidence/README.md)
