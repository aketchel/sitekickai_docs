---
description: >-
  If you are having issues after connecting your domain to Sitekick AI, please
  follow the steps below to correct resolve the issue.
---

# Issues Connecting Domain - Google

If you're having trouble connecting your custom domain to your Sitekick website (e.g., using Google Domains), follow these steps:

1. **Log into your domain registrar (e.g., Google Domains)**.
2. Locate the **DNS settings** for the domain you're trying to connect.
3. In the Sitekick dashboard, under **Site Editor → Domain Settings**, you'll see your DNS records. Copy:
   * **A Record** pointing to Sitekick’s IP address (e.g., `76.76.21.21`)
   * Optionally, **CNAME record** for `www` if using subdomains.
4. Paste these values into your Google Domains DNS records section.
5. Save and wait up to 24 hours for propagation.

**Still not working?**

* Make sure there are no conflicting records (e.g., existing A or CNAME records).
* Contact our support team if you're stuck
