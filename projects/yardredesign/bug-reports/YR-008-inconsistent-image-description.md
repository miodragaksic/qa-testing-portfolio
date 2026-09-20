# YR-008 — Inconsistent handling of image-description requests

**Type:** Functional / AI behavior  
**Severity:** Medium  
**Status:** Reproduced during exploratory testing

## Steps
1. Upload an image.
2. Ask the application to describe what is visible.
3. Observe routing and response.
4. Repeat with another image and a similar request.

## Expected
Equivalent image-description requests should follow a consistent supported flow and return a description, or consistently explain that the action is unsupported.

## Actual
Observed outcomes included:
- redesign/generation flow followed by interruption,
- **“Server returned invalid response.”**,
- successful image description on another similar request.

## Impact
The user cannot predict whether a simple image-understanding request will be handled as conversation, redesign, or error.

## QA note
No claim is made about the exact internal AI/backend cause.
