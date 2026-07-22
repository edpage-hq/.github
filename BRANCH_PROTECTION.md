# Branch protection

Unlike the other files in this set, branch protection isn't a file you commit —
it's a GitHub setting per repo (Settings → Branches, or Settings → Rulesets for
an org-wide ruleset applied to all repos matching a pattern, which is the
easier option once every starter uses the same branch name).

## Recommended settings for `master`

- **Require a pull request before merging**
  - Require at least **1 approval**
  - Dismiss stale approvals when new commits are pushed
- **Require status checks to pass before merging**
  - The CI job from the reusable workflow (`lint-test`) must be required
  - Require branches to be up to date before merging
- **Require conversation resolution before merging**
- **Do not allow force pushes**
- **Do not allow deletion of the branch**

## Applying it org-wide

If all starters use `master` as the default branch, a single **organization
ruleset** (Settings → Repository → Rulesets, at the org level) targeting
`master` across all repos is less error-prone than repeating the setup
manually on every new repo. Worth setting up once the first two or three
starters exist, so the ruleset can reference their actual CI job names.
