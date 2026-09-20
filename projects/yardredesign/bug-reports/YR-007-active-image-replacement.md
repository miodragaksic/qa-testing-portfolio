# YR-007 — Active image replacement is not explicit

**Type:** UX / Requirement clarification  
**Severity:** Medium  
**Status:** Observed; requirement should be confirmed

## Scenario
Multiple images are introduced during one chat and the user later refers to an earlier image.

## Expected
Either:
1. multiple images remain referenceable, or
2. a new image replaces the active working image and the UI clearly communicates this.

## Actual
Observed behavior suggests the newly uploaded image becomes the active working image. Referring to the previous image as “the first image” is not reliable, and replacement is not clearly communicated.

## Evidence note
The `imgs` counter alone is **not** treated as proof that an earlier image was deleted. A later isolated test showed a visible selected image did not necessarily change that counter.

## Suggested UX improvement
Display a clear state such as:

> New photo selected. Sending it will replace the current working photo.

The report does not require multi-image AI context.
