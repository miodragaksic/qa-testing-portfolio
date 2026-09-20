# YR-006 — Normal chat message enters image-generation UI state

**Type:** Functional / UX  
**Severity:** Medium  
**Status:** Reproduced

## Steps
1. Open a YardRedesign chat as a FREE user.
2. Enter a normal conversational question that does not request an image edit.
3. Press **Send**.
4. Observe progress/status UI before the text response.

## Expected
Handle the request as chat/text without showing a redesign/rendering workflow.

## Actual
The interface can enter a generation/rendering-style state before ultimately returning a normal conversational response.

## Impact
The user may believe image generation has started or that a generation credit may be consumed.

## QA note
This report describes visible black-box behavior; it does not assume the internal routing cause.
