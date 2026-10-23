---
description: Compare proposed CMS edits, approve the exact change, and understand draft, publication, undo and rollback controls.
---

# Review, publish and recover changes

Sitekick prepares work for review. A planning reply, a generated preview and a saved draft are different stages. Read the action label and current page status before approving: applying an edit to an already published page can change what visitors see immediately.

## Compare a page edit

1. Open **Pages** and choose **Open page**. The page workspace includes **Preview & edit**, **Changes**, **History** and **Page settings**.
2. In the visual workspace, choose **Load page preview**, select a section, paragraph or image, and describe the change. Choose **Revise selected text** or **Refine selected layout or replace a library image** as appropriate.
3. Choose **Prepare selected-element alternative**. Use **Refresh alternative** when the job is ready and compare **Current page** with **Alternative**. **Toggle mobile preview** helps inspect a narrower layout.
4. Choose **Review and approve in Activity** to inspect and save the result. A simplified structural preview may appear if a rendered preview is unavailable. Forms are disabled during inspection; it is not a successful form-delivery test.

For a conversation task, use **Review result here** to inspect before/after text or **Preview proposed design**, then **Approve and save draft** when appropriate.

## Save and publish deliberately

- **New content:** generation prepares a result; saving creates a draft. Where offered, use **Preview for publication**, check the saved preview, then **Publish changes** and confirm. You can also preview and publish in the advanced editor.
- **Alternative to an existing page:** saving the alternative leaves the original separate. Use **Compare changes** to open **Original** and **Draft** WordPress previews. Check desktop and mobile widths, then use **Publish changes** for a published original or **Save reviewed changes to original page** for an unpublished one. Applying preserves the original URL and publication status.
- **Direct revision:** if you selected **Update the selected page after review**, approval can apply to that page immediately, including a published page. Review its current status first.
- **Whole-site candidate:** follow the separate exact-release review and publication steps in [Whole-site projects](whole-site-projects.md).

An alternative is a comparison draft. It does not automatically split traffic or run an A/B test. Restricted embedded previews may limit navigation and forms; use the full saved previews and verify real interactions separately before launch.

## Undo and recovery have a scope

Open **Activity** or the page's **History** to find the saved job and its available controls.

- **Undo this revision** restores the captured previous page content when that revision supports undo. It can refuse if newer edits would be overwritten or you no longer have permission.
- **Restore original page** or **Restore the previous original** reverses a supported promotion of an alternative. Review the current state and any conflict message first.
- **Stop generation** stops or requests cancellation of work; it does not reverse edits already approved or erase usage already incurred.
- Whole-site **Review rollback** selects a previously published release and requires a new exact review and approval. It is distinct from undoing one page revision.

These controls are not a universal backup of plugins, orders, form submissions, DNS or every later edit. If a restore is blocked by newer work, keep the current state and ask support to help reconcile it. Do not repeatedly force a stale revision.

## Open the advanced tools

Use **Advanced editor** in the page workspace for Elementor layout and styling controls. **Advanced WordPress tools**, below **Ask Sitekick** in the top bar, opens WordPress page management. Page settings also provide advanced page and navigation links. Access depends on your WordPress permissions and installed tools; changes saved there follow that editor's own save and publication controls.

Older articles in [Using the Design Editor](../using-the-design-editor/README.md) may show a legacy editor. Match the editor you actually opened, and use this guide for the current CMS review flow.
