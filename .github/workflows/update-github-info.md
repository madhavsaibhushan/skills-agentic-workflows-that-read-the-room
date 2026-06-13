---
name: update-github-info
description: Draft GitHub Info website updates from official GitHub sources.
on:
  workflow_dispatch:
  schedule:
    - cron: '0 0 * * *'
permissions:
  contents: read
tools:
  edit: {}
  web-fetch: {}
safe-outputs:
  create-pull-request:
    title-prefix: "Update GitHub Info: "
    fallback-as-issue: false
network:
  allowed:
    - github.blog
    - github.com
---

# Update GitHub Info

Read `notes/mona-notes.md` before making any updates.

Use these sources:
- `https://github.blog/latest/`
- `https://github.blog/changelog/`

Update `site/content/github-info.md` with a concise summary of new GitHub Blog and Changelog content. Maintain markdown formatting, include dates and links, and keep the page focused on practical updates for readers.

Open a pull request for Mona to review using `safe-outputs.create-pull-request` so changes are proposed instead of written directly to `main`.

If no substantive update is needed, call `noop` with a short explanation rather than opening a pull request.
