# YR-009 — Misleading retry status when FREE generation limit is reached

**Type:** UX / Error handling  
**Severity:** Medium  
**Status:** Reproduced

## Preconditions
FREE-user session with FREE redesign quota exhausted.

## Steps
1. Attempt another redesign.
2. Observe quota message and main generation status.

## Expected
Clearly state that FREE quota is exhausted and when the next generation becomes available. Do not encourage an immediate retry that cannot succeed.

## Actual
The FREE-limit message reports a future reset period while the main status can simultaneously show:

> “Generation interrupted. Please try again.”

## Impact
Conflicting instructions may cause unnecessary repeated attempts.

## Suggested improvement
For quota responses, replace generic retry status with a dedicated **FREE limit reached** state and reset timer.
