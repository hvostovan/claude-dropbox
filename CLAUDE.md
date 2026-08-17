# claude-dropbox — agent notes

Purpose: one-way relay VPS → user's personal laptop. User's corporate VPN blocks direct access
to the VPS/Google Drive/OneDrive from the work environment, but GitHub is allowlisted. A
background script on the Windows laptop polls this repo (`git pull` every ~5s) to pull files
down. There is no pull-back path — treat this repo as VPS-to-laptop only.

## Workflow

- One folder per task/project (e.g. `openspec-sdd/`). When the user asks to "drop a file in
  dropbox/<project>", create/update it under that folder here (`/root/dropbox/` on the VPS),
  commit, and push straight to `main` — no branch, no confirmation needed, this is low-risk by
  design (routine per [[feedback-infra-change-workflow]] pattern: small/reversible → just do it).
- If the project folder doesn't exist yet, create it.
- Remote is `origin` → `git@github.com-dropbox:hvostovan/claude-dropbox.git`, using the
  `github.com-dropbox` SSH host alias (`/root/.ssh/config`), identity file
  `/root/.ssh/github_dropbox_deploy_key` (write-enabled deploy key, scoped to only this repo).

## Security notes

- Never commit secrets/credentials/keys here — this repo's whole purpose is to land content on
  a machine that periodically sits inside a corporate network perimeter.
- The Windows-side deploy key is read-only by design (added separately, see repo's GitHub
  deploy keys settings) — a compromise there can't push back to this repo.
- Don't reuse `/root/.ssh/github_progects_deploy_key` (the `server-infra` repo's key) here —
  keep deploy keys scoped one-per-repo, same convention as [[project-server-infra-repo]].
