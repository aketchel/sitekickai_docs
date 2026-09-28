# Sitekick documentation workflow

This repository is the canonical public source for Sitekick documentation. Sitekick's website syncs the Markdown and generates navigation, search, HTML pages, downloadable Markdown, and read-only MCP resources. GitBook is not required to edit, validate, or publish through the Sitekick workflow.

## Content roots

- `sitekick-documentation/`: Sitekick CMS documentation, served at the docs site root.
- `sitekick-studio-documentation/`: Sitekick Studio documentation, served under `/studio`.

Each product has its own `README.md` landing page and `SUMMARY.md` navigation tree. Keep customer-facing content here rather than maintaining duplicate source copies in the private application repository.

## Editing conventions

- Read the product's `SUMMARY.md` before editing. Keep its links, ordering, and page titles synchronized when adding, moving, or renaming articles.
- Preserve Markdown frontmatter, relative article links, heading anchors, and referenced assets. Validate that frontmatter parses; folded YAML descriptions are supported.
- Keep relative article links within their product content root. Use canonical `https://docs.sitekick.ai/` URLs for links between products.
- Preserve existing public URLs where possible. Coordinate any URL changes with the website's routing and migration mappings.
- Follow the existing Markdown and GitBook-compatible schemas and block structure. Do not introduce blocks that the Sitekick renderer cannot handle.
- Preserve existing `gitbook-docs.yaml`, `.gitbook/`, and other sync metadata until the integration is explicitly retired. Moving away from GitBook does not itself authorize deleting that metadata.

## Review and publishing

- Create changes on a feature branch from the latest `origin/main` and open a pull request to `main`.
- Validate `SUMMARY.md` targets, relative links, frontmatter, and asset references before merging.
- When the Sitekick application checkout is available, run `npm run docs:sync`, build the docs, and check affected pages in the Sitekick preview. Changes to content roots must also update `shared/docs/sources.js` and relevant generator tests in that application.
- The website's rebuild/release workflow publishes generated output. A commit to this repository alone is not evidence that the live site has updated; verify the deployed pages after release.
- Use GitHub diffs and Sitekick previews for review. A GitBook account, import, change request, or preview link is not a required gate.

## Optional tooling

The GitBook writing skill can be used as a formatting reference when helpful. Installing or updating it is optional. Its GitBook-specific publishing and preview procedures do not replace the Sitekick workflow above.

Do not commit locally installed skills, skill lockfiles, or generated agent configuration unless explicitly requested.
