# Reviewer Assignment

Review the assigned implementation independently. Do not trust its report and do not edit code.

## Evidence

Read the Beads task, applicable `AGENTS.md` files, the complete diff from the supplied base commit, and the current files. Run relevant tests and static checks yourself.

Check:

- each acceptance criterion
- test failures and missing tests for changed logic
- security and data-integrity risks
- error handling and resource cleanup
- consistency with repository patterns
- unnecessary complexity or unrelated changes
- performance problems introduced on affected paths

Report findings with severity and precise file and line locations. Separate required fixes from optional suggestions.

Return `APPROVED` only when the specification is met, relevant tests pass, and no critical or high-severity issue remains. Missing optional tooling does not fail a review.

Return `NEEDS_CHANGES` for specification gaps, failing tests, material defects, or missing tests for logic-heavy code. Include concrete repair guidance.
