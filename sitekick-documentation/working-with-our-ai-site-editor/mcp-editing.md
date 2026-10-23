---
description: Understand CMS editing through MCP, required setup and permissions, supported tools, and browser approval for publication.
---

# Edit Sitekick CMS through MCP

MCP lets a compatible assistant work with Sitekick's structured website-project tools. **Editing access requires setup and account authorization.** The presence of CMS editing code or an MCP option in an assistant does not mean every customer can connect today. Ask Sitekick support whether the editing service and your intended client are enabled for your account, and obtain the approved connection instructions.

The documentation site's read-only MCP connection supplies help articles. It does not grant CMS editing access. This article describes the separate CMS editing service, not Studio custom applications. Studio remains unlaunched.

## Prerequisites and connection

- Sitekick must enable and configure the CMS MCP service with a reachable HTTPS endpoint and register the client's exact redirect URLs. Self-service dynamic client registration is not supported. Do not guess an endpoint from the CMS or documentation URL.
- Use a client that supports the service's Streamable HTTP and OAuth flow. A particular ChatGPT or other assistant connection must be confirmed separately; protocol support alone is not proof of an available live integration.
- Your Sitekick account needs current access, ownership of the selected website and the permissions required for the requested operation. Generation uses credits; creating a website also needs an available website slot. There is no verified public promise that a named plan includes an immediately usable MCP connection. Check current account eligibility with support before changing plans for MCP.

After receiving approved setup instructions, add the provided service in your supported client, sign in through Sitekick's WordPress login, and inspect the named client and requested scopes on **Connect Sitekick**. Choose **Allow connection** only for the access you intend to grant. You should not paste passwords, access tokens or service credentials into a conversation.

| Scope | Purpose |
| --- | --- |
| `sites:read` | Discover authorized websites and read project, job and release information |
| `sites:write` | Prepare and update projects and perform supported generation/editing operations |
| `sites:create` | Create a website, subject to current account eligibility and quota |
| `sites:publish` | Carry an exact approved publication or rollback request; browser approval is still required |

OAuth consent does not approve publication. Sitekick rechecks account access, website ownership and capabilities on requests; an old connection cannot override a current denial.

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

## A safe working sequence

1. Ask the assistant to list authorized websites and let you select the exact target. It must retain the returned `site_ref`; a display name or WordPress page number is not a substitute.
2. Inspect capabilities, create or update a project blueprint, and review the intended revision before sealing it.
3. Request the generation estimate. Review its credit context before explicitly starting generation with the returned estimate identity. A changed revision or pricing requires a fresh estimate.
4. Follow the saved job's status, prepare its completed release and request a preview.
5. Follow the returned WordPress browser continuation. Sign in as the authorized owner and review the exact candidate there.
6. Approve publication in that browser review. The assistant can then retrieve review status and carry the exact approved publication request. A “yes” in the assistant chat cannot replace browser approval.

For example: “List my authorized websites, let me choose one, then prepare a Services-page refinement for review. Show the estimate before starting generation and stop for my browser publication approval.”

Existing-site capture also requires the returned owner-browser continuation and confirmation. It is not a general remote-site crawler or a full plugin/database migration tool.

## Disconnect and recover

Use **Connected apps** in your Sitekick account to inspect active connections and choose **Disconnect**. Disconnect prevents new authorized calls; token expiry or disconnect does not necessarily cancel a durable job already accepted. Inspect its status and use the explicit cancellation control if appropriate. Cancellation is not undo.

If a mutation times out or returns an unknown outcome, check saved job/project/release status first. Preserve the original request and idempotency key for recovery; do not ask the assistant to recreate the operation with a fresh key. If access is denied, confirm the correct account, website, granted scopes and current entitlement. If connection setup is unavailable, contact support rather than creating credentials or repeatedly reconnecting.

See [Whole-site projects](whole-site-projects.md) for the browser flow and [Saved work and queue troubleshooting](../i-encountered-problems-how-do-i-fix-them/saved-work-and-queues.md) for stalled work.
