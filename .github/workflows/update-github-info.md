---
name: update-github-info
description: Draft website updates for Mona's GitHub Info page from official GitHub sources.
on:
  workflow_dispatch:
  schedule:
    - cron: '0 0 * * *'
permissions:
  contents: read
safe-outputs:
  create-pull-request:
    title-prefix: "Update GitHub Info: "
    fallback-as-issue: false
tools:
  edit: {}
  web-fetch: {}
network:
  allowed:
    - github.com
    - github.blog
---

# Update GitHub Info

Read `notes/mona-notes.md` before making any updates.

Use these official sources:
- `https://github.blog/latest/`
- `https://github.blog/changelog/`


Update `site/content/github-info.md` with a concise summary of new GitHub Blog and Changelog content. Maintain markdown formatting, include dates and links, and keep the page focused on practical updates for readers.

Before opening pull request check the workflow used mona's notes,github blog(https://github.blog/latest/),github changelog(https://github.blog/changelog/)

Open a pull request for Mona to review. Use `safe-outputs.create-pull-request` so the workflow proposes changes instead of writing directly to `main`.

If no substantive update is needed, call `noop` with a short explanation rather than opening a pull request.
