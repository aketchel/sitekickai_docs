---
description: 'Note: A records are not required for subdomains.'
---

# How can I connect a subdomain to my landing page?

If you want your Sitekick landing page to appear on a subdomain (like promo.yourdomain.com), here’s how to set that up:

Log in to your domain registrar (like GoDaddy, Namecheap, etc.).

Go to your domain’s DNS settings.

Add a new CNAME record with the following details:

Name/Host: The subdomain you want to use (e.g., promo)

Type: CNAME

Value/Points to: Your Sitekick-hosted URL (we’ll provide this in your dashboard or support materials)

Save the record.

⚠️ Important: DNS changes can take up to 24–48 hours to fully update across the internet.

Once connected, your landing page will load directly from the subdomain you’ve chosen.



NOTE: Instead of `www` for the CNAME record, add the following subdomain value:



**CNAME**

* _Host_: store (for example). This replaces `www`.
* _Points to_: s.multiscreensite.com

After configuring the CNAME record for your subdomain, you should have the following CNAME record in your DNS settings:



<figure><img src="../.gitbook/assets/image (226).png" alt=""><figcaption></figcaption></figure>

Once done setting up the CNAME records, proceed to publishing your site as usual and assigning the subdomain by [following this guide](how-to-connect-your-domain.md) on how to connect your domain.

_When assigning a subdomain to a site ,`www` does not need to be added, just the subdomain, for example store.domain.com._
