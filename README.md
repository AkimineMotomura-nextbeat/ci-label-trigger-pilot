# ci-label-trigger-pilot

Sandbox for verifying a label-triggered CI design (no CI on push; explicit
`run-ci` label dispatches CI; merge is gated by a required status check).

## What this verifies (Step 0)

1. Adding the `run-ci` label to a PR dispatches `ci.yml` on the PR head branch.
2. Check runs from the `workflow_dispatch` run attach to the PR head SHA and
   satisfy the `ci-gate` required status check in the merge box.
3. A new push invalidates the check (merge box returns to blocked).
4. Unrelated labels do not affect the merge box.

Dummy CI only — nothing real is built or tested here.
