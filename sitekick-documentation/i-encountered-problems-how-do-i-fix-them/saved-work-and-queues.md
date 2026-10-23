---
description: Recover queued or interrupted CMS work without submitting duplicate generation requests.
---

# Saved work and queue troubleshooting

Sitekick saves background work on the server. Closing a tab or losing a response does not prove that generation stopped. A second prompt can start separate work and incur additional credit usage.

## Check before retrying

1. Return to the same account and website. For a conversation, choose **Load conversations**, select the saved conversation and **Refresh progress**.
2. Open **Activity** â†’ **Refresh activity**, or the page's **Changes** and **History**, to check the saved job. For whole-site work, select the original website and use **Refresh status** or **Continue saved work**.
3. Read the state and message. **Queued** means saved and waiting; **running** means processing; **ready** means there is a result to review; a saved/applied draft may still need explicit publication.
4. For failed work, use the existing job's **Resume saved generation**, **Retry generation** or **Retry / recover job** only after checking its status and the displayed error. Recovery may still use credits for unfinished work; do not assume every retry is free.

If the status is uncertain, keep the original job and request identity. Avoid new conversations, fresh prompts, repeated Generate clicks or a new MCP idempotency key as a workaround.

## Common problems

| Symptom | Next step |
| --- | --- |
| Response timed out | Refresh saved progress before submitting again; the server may have accepted the work |
| Queued with no progress after refreshing | Keep the saved job; contact support so the background dispatcher can be checked |
| Estimate unavailable or credits/access denied | Check Usage, membership and configuration; resolve the specific account issue before generation |
| Session expired or preview asks for login | Sign in to the intended CMS account and reload the same saved work or review |
| Conversation changed / reload requested | Reload the saved conversation before saving another decision or approving a task |
| Proposed task failed validation | Read the saved request and message; no task execution is implied. Check for saved jobs before deliberately sending a corrected, focused request |
| Undo refused because of newer edits | Preserve the newer work and reconcile the changes; do not force the old revision |
| Wrong website shown | Select the intended website explicitly; existing jobs retain their original target |
| Preview does not match the live website | Check whether you saved an alternative, approved its application and completed publication for that exact result |

Use **Stop this planning job**, **Stop generation** or **Request cancellation** when appropriate. Stopping planning and stopping an already approved draft task are separate actions. Cancellation does not undo saved or published changes, and completed usage can still be charged.

When contacting support, share the website/project/job identifier, approximate time, visible state and a short description of what you clicked. Use a private support channel for account details. Never post credentials, signed private-preview URLs, customer content or raw logs in public issues.
