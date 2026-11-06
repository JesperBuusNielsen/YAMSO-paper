# Collaboration protocol

- Use one `.tex` file per substantial section.
- Coordinate ownership of a section during large edits.
- Overleaf collaborators may edit directly in the shared project. Local
  integration reads both its direct Git remote and the GitHub remote.
- Use `pull-sync` before local editing and `full-sync` to publish the merged
  paper to both places; see [OVERLEAF.md](OVERLEAF.md).
- Resolve overlapping changes locally and compile the merged result.
- Do not edit the same paragraph concurrently in Overleaf and locally.
- GitHub pulls can displace Overleaf comments and tracked changes. Resolve them
  or preserve the discussion elsewhere before synchronizing.
- Keep downloaded papers, correspondence, research notes, and provisional
  arguments out of this public repository.
- Never force-push `main`.
