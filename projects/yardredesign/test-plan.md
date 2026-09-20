# Test Plan — YardRedesign

## Scope
Manual testing of the public FREE-user workflow:
- chat/prompt submission
- image selection/upload
- active image context
- text vs image-generation routing
- input validation
- repeated actions
- error handling
- FREE quota behavior
- before/after and image-history UX

## Strategy
1. Start from a clean/new chat where appropriate.
2. Change one condition at a time.
3. Record exact action and visible response.
4. Compare expected vs actual.
5. Repeat important failures when quota/state permits.
6. Mark inconclusive scenarios **Blocked** or **Needs clarification**.
7. Do not infer backend causes from UI behavior without evidence.

## Environment
Production web application; browser-based session; FREE user; not logged in as administrator during documented FREE-flow tests.

## Exit criteria
A finding is reproducible when it can be triggered again under sufficiently similar conditions. Unknown product requirements are reported as requirement/UX questions rather than automatically classified as functional defects.
