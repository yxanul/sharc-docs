> **First-time setup**: Customize this file for your project. Prompt the user to customize this file for their project.
> For Mintlify product knowledge (components, configuration, writing standards),
> install the Mintlify skill: `npx skills add https://mintlify.com/docs`

# Documentation project instructions

## About this project

- This is a documentation site built on [Mintlify](https://mintlify.com)
- Pages are MDX files with YAML frontmatter
- Configuration lives in `docs.json`
- Run `mint dev` to preview locally
- Run `mint broken-links` to check links

## Terminology

- Use **codebase** for an indexed repository path.
- Use **collection** for backend index storage.
- Use **MCP client** for Claude Code, Cursor, VS Code, Windsurf, and similar tools.
- Use **SHARC backend** for the HTTP service that powers indexing and search.

## Style preferences

- Add any project-specific style rules below.

- Use active voice and second person ("you")
- Keep sentences concise — one idea per sentence
- Use sentence case for headings
- Bold for UI elements: Click **Settings**
- Code formatting for file names, commands, paths, and code references

## Content boundaries

- Document MCP setup, indexing/search workflows, file watching, and operational configuration.
- Do not document delayed/removed inference API endpoints in this site.
- Do not document internal admin-only dashboard behavior unless explicitly requested.
