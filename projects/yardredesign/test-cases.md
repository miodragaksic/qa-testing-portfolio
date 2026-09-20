# Test Cases — YardRedesign

| ID | Scenario | Steps | Expected | Observed | Result |
|---|---|---|---|---|---|
| TC-001 | Empty Send | Leave input empty → Send | Validation; no request | “Write a message or upload a photo.” | PASS |
| TC-002 | Rapid repeated Send | Enter message → Send twice quickly | One request; no duplicate | No duplicate; second action reached empty validation | PASS / UX observation |
| TC-003 | Normal chat question | Send non-edit conversational question | Text response without redesign state | Generation-style UI can appear first | FAIL |
| TC-004 | Describe uploaded image | Upload image → ask what is visible | Consistent description or clear unsupported message | Generation/interruption/error vs successful description across attempts | FAIL |
| TC-005 | Reference previous image | Image A → image B → refer to “first image” | Previous image referenceable or replacement clearly stated | B appears active; A not reliably referenceable | NEEDS CLARIFICATION |
| TC-006 | FREE quota reached | Exhaust quota → attempt redesign | Clear quota state and consistent guidance | Quota timer plus generic “Please try again” | FAIL |
| TC-007 | Image counter semantics | Select/upload image → observe `imgs` | Counter meaning clear/consistent | Visible image did not necessarily increment counter | NEEDS CLARIFICATION |

## Notes
TC-005 is not presented as a confirmed multi-image functional defect. A one-active-image design may be valid; the replacement behavior should be explicit.

TC-007 shows why a UI counter alone should not be treated as proof of data deletion.
