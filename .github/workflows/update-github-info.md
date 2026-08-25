---
name: update-github-info
description: Keep the GitHub Info website current with practical updates from GitHub's public channels.
on:
  schedule: daily
  workflow_dispatch:
permissions:
  contents: read
engine: copilot
tools:
  github:
    toolsets: [repos]
  web-fetch:
  edit:
network:
  allowed:
    - github.blog
    - github.com
safe-outputs:
  create-pull-request:
    title-prefix: "[mona] "
    labels: [documentation, automation]
    draft: true
    max: 1
---

# Update GitHub Info

Keep the GitHub Info website useful, concise, and current for developers.

## Instructions

1. Read `notes/mona-notes.md` from this repository before making any changes.
2. Use the GitHub repository API tools to read repository guidance and reference files. Do not use the terminal, CLI, or sandboxed commands for repository guidance or reference-file reads.
3. Use web fetch to read:
   - https://github.blog/latest/
   - https://github.blog/changelog/
4. Select only practical, relevant updates that help developers learn GitHub faster. Cite the source in each update as either the GitHub Blog or GitHub Changelog.
5. Update `site/content/github-info.md` with concise summaries. Preserve useful existing content and avoid duplicate entries.
6. Review the resulting file for clarity, accuracy, and valid Markdown.
7. Create a pull request containing the changes for Mona to review. Do not write directly to the default branch.
