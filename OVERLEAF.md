# Synchronizing the paper with Overleaf

The shared paper has two Git remotes:

- `origin`: <https://github.com/JesperBuusNielsen/YAMSO-paper.git>
- `overleaf`: <https://git@git.overleaf.com/6a9ac684999d2b168508646c>

The Overleaf project is
<https://www.overleaf.com/project/6a9ac684999d2b168508646c>.
Its main document is `main.tex`, compiled with pdfLaTeX.

Overleaf edits are fetched directly from its Git remote. GitHub Desktop's
Fetch/Pull for `origin` alone does not retrieve edits that exist only on
Overleaf. The sync procedure merges both histories before publishing.

## Named sync requests

When working with the assistant, use these phrases:

- **`pull-sync`**: fetch and merge changes from GitHub and Overleaf into the
  local paper, preserve local edits, make any necessary local checkpoint
  commits, and rebuild the PDF. No remote is pushed.
- **`full-sync`**: do the above, then commit and push the merged shared paper
  to both GitHub and Overleaf. This request authorizes the required commits
  and pushes. Verify that both remotes contain the same resulting commit.

These are workflow requests, not installed terminal commands. The private
workspace records the shared-paper revision separately; only this shared
repository is sent to Overleaf.

## Local integration

Inspect and preserve local changes before merging. Stage named, reviewed
files rather than every untracked file. Fetch both remotes and integrate
`origin/main` and `overleaf/main` into local `main`, fast-forwarding when
possible and creating a merge commit if histories diverge. Resolve mechanical
conflicts locally; discuss ambiguous changes to the mathematics or prose.

Run `make` after integration. The current PDF is `output/pdf/main.pdf`.
Recheck the remote heads before publishing, incorporate any new edits, then
push to both remotes without force. Verify both remote heads after the push;
report separately if only one destination succeeded.

## Editing together

Prefer separate sections during substantial edits. Overleaf collaborators
can keep editing in the project; the next sync retrieves their source edits.
Avoid concurrent edits to the same paragraph when possible. Overleaf review
comments and tracked-change metadata are not a substitute for source changes
in Git; preserve discussion that must survive synchronization separately.
