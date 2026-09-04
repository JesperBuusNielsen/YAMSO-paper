# Connecting this repository to Overleaf

The GitHub connection is owned by the Overleaf project owner. The owner must
have an Overleaf plan that includes GitHub synchronization and a GitHub account
with write access to `JesperBuusNielsen/YAMSO-paper`.

## One-time setup for the Overleaf project owner

1. Send Jesper the GitHub username that will be connected to Overleaf. Accept
   the GitHub collaborator invitation for `JesperBuusNielsen/YAMSO-paper`.
2. In Overleaf **Account Settings**, connect that same GitHub account.
3. From the Overleaf dashboard choose **New Project -> Import from GitHub**.
4. Select `JesperBuusNielsen/YAMSO-paper`. Do not start with an existing
   Overleaf project: Overleaf cannot link an existing project to an existing
   GitHub repository.
5. Open the imported project and confirm that `main.tex` is the main document
   and that the compiler is **pdfLaTeX**.
6. Invite the other authors to the new Overleaf project in the usual way.

Only the project owner performs the initial GitHub connection. Afterward,
every collaborator in the Overleaf project can use its synchronization button.

## Normal editing cycle in Overleaf

GitHub synchronization is manual, not continuous.

1. Announce which section you intend to edit.
2. Open **Integrations -> GitHub** and choose **Pull GitHub changes**.
3. Make the edit and compile the complete document in Overleaf.
4. Resolve comments or tracked changes associated with the edited text.
5. Open **Integrations -> GitHub**, choose **Push Overleaf changes to GitHub**,
   and enter a short descriptive commit message.
6. Tell the other authors that the GitHub version has changed.

Do not edit the same paragraph concurrently in Overleaf and in a local clone.
A GitHub pull can displace Overleaf comments or tracked changes, so those are
not a durable substitute for an issue, email, or manuscript text.

## Normal local cycle

From the public paper checkout:

```sh
git pull --ff-only
make
git status
git add <reviewed-files>
git commit -m "Describe the manuscript change"
git pull --rebase
make
git push origin main
```

The `git add` step must name only reviewed manuscript files. Generated build
products belong under `output/` and are ignored.

## If Overleaf reports a conflict

Stop editing and do not force either side. Overleaf may place its version on a
new GitHub branch instead of updating `main`. Send the branch name to Jesper;
the versions can then be merged locally or through a GitHub pull request,
compiled, and pushed back to `main`. Once `main` is resolved, pull it into
Overleaf before resuming work.

Official documentation:
<https://docs.overleaf.com/integrations-and-add-ons/git-integration-and-github-synchronization/github-synchronization>
