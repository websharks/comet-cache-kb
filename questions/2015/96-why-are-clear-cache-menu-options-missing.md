---
title: Why are Clear Cache menu options missing?
categories: questions
tags: clearing-the-cache, 
author: raamdev
toc-enable: off
github-issue: https://github.com/websharks/comet-cache-kb/issues/96
---

The Clear Cache menu options in the WordPress Admin Bar, will change depending on which Comet Cache and server features are enabled. It will also change depending on your current context within WordPress itself.

**Note:** If you don't currently see these menu options, you can enable them in **WordPress Dashboard → Comet Cache → Plugin Options → Manual Cache Clearing**.

![2015-10-31_21-01-56](https://cloud.githubusercontent.com/assets/53005/10867073/9e46ca8c-8025-11e5-8383-4872f5555adf.png)

There are three menu options that are dynamic:

**Current URL**: The "Current URL" option only shows on the front-end of the site. You won't see this while working in the Dashboard; i.e., in `/wp-admin/*` areas. Since Comet Cache does not cache WordPress Dashboard pages, it doesn't make sense to show a "Current URL" option when you are on the WordPress Dashboard.

**OPCache**: The "OPCache" option only shows if the PHP OPCache extension is running on the server, and only if the current user has capabilities that allow them to `update_plugins` (or `manage_network_plugins` on a Multisite Network).

**CDN Cache**: The "CDN Cache" option only appears if Static CDN Filters are enabled (see **WordPress Dashboard → Comet Cache → Plugin Options → Static CDN Filters**), and only if the current user has capabilities that allow them to `update_plugins` (or `manage_network_plugins` on a Multisite Network).
