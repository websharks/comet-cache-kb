---
title: Is Comet Cache compatible with iThemes Security?
categories: questions
tags: themeplugin-developers, troubleshooting
author: renzms
github-issue: https://github.com/websharks/comet-cache-kb/issues/130
toc-enable: off
---

Yes, Comet Cache is compatible with iThemes Security and other WordPress security plugins that are used to protect a WordPress site.

WordPress plugins, such as iThemes Security, may block parts of the WordPress site, including the back-end administration, thus preventing unauthorized visitors from accessing these areas. iThemes Security may also tweak certain features on the Dashboard and/or host file settings for increased security. Comet Cache causes no conflict with iThemes Security in this regard, and enabling most of the recommended settings in the Lite version of iThemes Security has no reported issues with the caching process.

There are no specific features that need to be configured for Comet Cache to work with iThemes Security.

### What if iThemes Security constantly warns me when Comet Cache caches or clears files?

iThemes Security and other WordPress security plugins may log changes to your site files and notify you of these changes. Comet Cache is a dynamic plugin that quietly caches pages, and depending on your specified configuration(s), it is able to automatically clear, wipe or update the cache on a specified date or upon a triggered event. These automatic changes may be picked up by the security plugin and reported as unsolicited changes. These notifications are false-positives.

This issue can be resolved in iThemes Security by excluding the cache directory from being monitored in the **WP Dashboard → Security → Settings → File Change Detection → Settings** section of iThemes Security.

![iThemes Security: File Change Detection settings](https://cloud.githubusercontent.com/assets/13220018/22107756/9a457ce8-de8a-11e6-9488-5b77db28fa39.png)

In the pop-up window, scroll down to the **Files and Folders List** section. Exclude files or folders by clicking the red minus next to the file or folder name. We suggest whitelisting `wp-content/cache/comet-cache/`, or you could whitelist the entire cache directory; i.e., `wp-content/cache`.

![iThemes Security: Files and Folders List](https://cloud.githubusercontent.com/assets/13220018/22107874/506866ca-de8b-11e6-97b8-411fcbd07655.png)
