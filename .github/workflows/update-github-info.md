---
name: update-github-info
description: Draft website updates for Mona's GitHub Info site from official GitHub sources.
model: gpt-4.1
on:
  workflow_dispatch:
  schedule:
    - cron: '17 9 * * *'
safe-outputs:
  create-pull-request:
    title-prefix: "[mona] "
    draft: true
    fallback-as-issue: false
tools:
  edit:
  web-fetch:
network:
  allowed:
    - github.blog
    - github.com
    - awesome-copilot.github.com
---

# Update Mona's GitHub Info website

Read `notes/mona-notes.md` before making changes.

Use web-fetch to read these official sources:

- GitHub Blog: https://github.blog/latest/
- GitHub Changelog: https://github.blog/changelog/
- Awesome Copilot workflows: https://awesome-copilot.github.com/workflows/

Read repository guidance or reference files with GitHub repository API tools.
Do not use terminal, CLI, or sandboxed commands to read repository guidance or
reference files.

Update `site/content/github-info.md` with concise, practical updates that help
developers learn GitHub faster. Mention the source whenever an update comes
from the GitHub Blog or GitHub Changelog.

Open a pull request for Mona to review. Use a pull request title that mentions
Mona or GitHub Info. Do not write directly to `main`; use the `safe-outputs`
`create-pull-request` output so the proposed changes stay reviewable.

Check that the agentic workflow configuration syntax is valid before finishing.
Do not compile this workflow.