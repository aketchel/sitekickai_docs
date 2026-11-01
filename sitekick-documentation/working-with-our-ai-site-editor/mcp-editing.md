---
description: Connect ChatGPT to Sitekick MCP, authorize website access, edit draft projects, and review generation and publication safely.
---

# Edit Sitekick CMS through MCP

MCP lets ChatGPT and compatible assistants read and edit Sitekick website projects after you authorize your account. Use the website-editing server at **`https://mcp.sitekick.ai/mcp`**.

## Choose the right MCP server

- **Website editing:** `https://mcp.sitekick.ai/mcp` works with your Sitekick CMS websites and projects. Sitekick sign-in and OAuth consent are required.
- **Public help articles:** `https://docs.sitekick.ai/mcp` searches and reads documentation. It does not grant access to your websites.

The documentation site's **Connect with MCP** control connects the read-only help service. To edit a website, add the website-editing endpoint above separately. This guide covers Sitekick CMS; Studio custom applications remain unlaunched.

## Connect ChatGPT to Sitekick

You need a Sitekick account with current access to the intended website and a ChatGPT account/workspace that permits custom MCP servers. Your current Sitekick permissions, credits and website slots still apply. If the custom-server option is unavailable, check your ChatGPT workspace policy or ask its administrator.

1. Open **Plugins** in ChatGPT, select the **plus** button, then **Add custom MCP server**.
2. Give it a recognizable name, such as **Sitekick website editor**, and enter `https://mcp.sitekick.ai/mcp` as the public server URL, including `/mcp`.
3. Select **OAuth** authentication. Use the discovered public-client connection; Sitekick supports Client ID Metadata Documents (**CIMD**) and dynamic client registration (**DCR**). You do not need a client secret. If your client requires a secret or manual preregistration, check compatibility with Sitekick support rather than inventing credentials.
4. Review ChatGPT's warning and discovered tools, then create and install the plugin. ChatGPT's labels and availability can vary by account; see [OpenAI's current connection instructions](https://developers.openai.com/plugins/deploy/connect-chatgpt).
5. Connect your Sitekick account when prompted, including on the first tool call. Sign in through Sitekick's browser login. On **Connect Sitekick**, check the named client, callback destination and requested permissions before choosing **Allow connection**.
6. If offered, choose whether to **Keep this app connected**. Continued access requires your consent and still expires or can be revoked; reconnect when asked. It does not grant extra permissions.
7. Start a new conversation, type `@` and select the installed Sitekick plugin. Begin with: "List my authorized Sitekick websites. Do not change anything yet."

Never paste your password, tokens or service credentials into a chat. Registration identifies the assistant; your Sitekick login and consent authorize access. OAuth consent does not approve publication.

Other clients must support Streamable HTTP and the server's public OAuth flow. CIMD/DCR support alone does not establish that every assistant or product has been tested. If a manually configured client needs a callback, use its actual displayed redirect URI and support guidance.

## Choose permissions

Grant only the access needed for your task. Where your client supports scope selection, request the appropriate scopes below, then review the actual Sitekick consent screen. To change granted access, reconnect and consent to the new scope set.

| Scope | Purpose |
| --- | --- |
| `sites:read` | Discover authorized websites and read project, job and release information |
| `sites:write` | Prepare and update projects and perform supported generation/editing operations |
| `sites:create` | Create a website, subject to current account eligibility and quota |
| `sites:publish` | Carry an exact approved publication or rollback request; browser approval is still required |

Sitekick rechecks account access, website ownership and capabilities on requests; an old connection cannot override a current denial.

## Supported tool names

The CMS contract defines these tools. A configured service's discovery response and current permissions determine what you can actually call.

- **Choose and inspect a website:** `sitekick_site_list`, `sitekick_site_inspect`
- **Find/select an owned existing website:** `sitekick_site_existing_list`, `sitekick_site_existing_select`
- **Create a website:** `sitekick_site_create`
- **Request supported existing-site capture:** `sitekick_adoption_capture`
- **Plan and revise a blueprint:** `sitekick_project_create`, `sitekick_project_get`, `sitekick_project_update`, `sitekick_project_seal`
- **Review generation credits:** `sitekick_project_estimate`
- **Start, inspect, cancel or recover generation:** `sitekick_job_start`, `sitekick_job_get`, `sitekick_job_cancel`, `sitekick_job_retry`
- **Prepare and inspect an immutable release:** `sitekick_release_prepare`, `sitekick_release_get`
- **Preview and review:** `sitekick_release_preview`, `sitekick_release_review`, `sitekick_release_review_get`
- **Apply exact approved publication or rollback:** `sitekick_release_activate`, `sitekick_release_rollback`
- **Use reusable templates:** `sitekick_template_list`, `sitekick_template_get`, `sitekick_template_create`
- **Select supported existing integrations:** `sitekick_binding_choices`, `sitekick_binding_enroll`

## Work on a draft before publishing

1. **Choose the website.** Ask the assistant to list your authorized websites, select the exact target, and inspect its capabilities. Retain the returned `site_ref`; a display name or WordPress page number is not a substitute. Confirm the target again before changing anything.
2. **Plan and inspect.** Create or load a project, read its current blueprint, and request a small, specific change. Review the updated project before sealing that revision. Creating or updating a project saves planning work; it does not generate or publish a WordPress page.
3. **Review the estimate.** Ask for the generation estimate and its credit context. Explicitly approve generation only after reviewing it. Generation uses credits; creating a website also requires an available website slot. A changed revision or pricing requires a fresh estimate.
4. **Follow saved work.** Track the returned job until it reports completion. Load the completed release and inspect the returned page and preview status. An accepted job or generated content alone does not prove that WordPress/Elementor pages have been created or that anything is live. If pages or a preview are unavailable, stop and use the recovery guidance below.
5. **Preview privately.** Prepare the completed release where supported and open its returned preview. Check each page, links, content and target website. Follow the returned WordPress browser continuation and sign in as the authorized owner.
6. **Review publication separately.** Inspect the exact candidate and impact in the browser review, then approve that exact publication. The assistant can retrieve the review status and carry the matching approved publication request. A "yes" in chat and OAuth consent cannot replace browser publication approval. A changed candidate needs a new review.
7. **Verify the result.** Read the release status and open the actual live pages after activation. A successful project edit, generation or private preview is not publication confirmation. Rollback also needs its own exact browser review and approval.

For a first draft-only test, try:

> List my authorized Sitekick websites and let me choose one. Inspect it, then create a draft project for a Services page using facts I provide. Read back the saved project and update only its proposed headline. Do not start generation or publish.

When ready to continue:

> Load this saved project and confirm its website. Show the current revision and generation estimate. Ask before starting generation, then inspect the completed job and private preview. Stop for my browser publication approval.

Existing-site capture also requires the returned owner-browser continuation and confirmation. It is not a general remote-site crawler or a full plugin/database migration tool.

## Troubleshoot and reconnect

- **Only help articles appear:** you connected the documentation MCP. Add `https://mcp.sitekick.ai/mcp` and authorize your Sitekick account separately.
- **Connection or sign-in fails:** check the full endpoint, OAuth selection and correct Sitekick account. Refresh the client's connection metadata if available, then reconnect and complete a fresh consent flow. If it asks for a client secret, contact support with the client name and error; do not paste secrets into chat.
- **Access denied or a website is missing:** check ownership, account access, granted scopes and current capabilities. Reconnecting cannot override missing account permissions or quota.
- **Project input is rejected:** have the assistant read the tool's current input schema and validation message, correct the named fields and resubmit only after confirming the request was rejected. Describe your business, intended pages and approved facts clearly; do not guess internal identifiers or substitute a page number for `site_ref`.
- **A write times out or its outcome is unknown:** inspect the saved project, job or release before retrying. Preserve the original request and idempotency key for recovery. Do not create a fresh operation or key merely because the response was lost.
- **Generation is incomplete, pages are missing or preview fails:** inspect the saved job and release status, then use the offered recovery controls. Do not treat a project ID or generated content as a ready WordPress/Elementor page. Contact support with the non-secret job/release ID and error if recovery is unavailable.
- **Publication is refused:** return to the browser review for the exact candidate and target. Confirm your publication permission and approval status; do not try to bypass the review through chat.

## Disconnect access

Use **Connected apps** in your Sitekick account to inspect active connections and choose **Disconnect**. This revokes the connection's authority for new calls. You can also remove the plugin in your assistant; use Sitekick's disconnect control to revoke server-side access. To connect again, complete a fresh login and consent flow.

Disconnecting or token expiry does not necessarily cancel a durable job already accepted. Inspect its status and use the explicit cancellation control if appropriate. Cancellation is not undo.

See [Whole-site projects](whole-site-projects.md) for the browser flow and [Saved work and queue troubleshooting](../i-encountered-problems-how-do-i-fix-them/saved-work-and-queues.md) for stalled work.
