---
title: Static CDN Filters for WordPress Multisite Networks
categories: tutorials
tags: static-cdn-filters, wp-multisite
author: raamdev
github-issue: https://github.com/websharks/comet-cache-kb/issues/73
---

The Comet Cache Static CDN Filters are fully compatible with WordPress Multisite Networks and this KB Article will outline a few common Multisite Network scenarios and offer suggestions for how to configure the Static CDN Filters for your specific scenario. 

The three common WordPress Multisite Network scenarios are Multisite with Sub-Directories (for which you can configure a single CDN Domain Name, or multiple CDN Domain Names to take advantage of Domain Sharding), Multisite with Sub-Domains, and Multisite with Domain Mapping.

## WordPress Multisite w/ Sub-Directories

This is the default configuration when you first setup a WordPress Multisite Network. When running in sub-directory mode, your child sites all reside under the same top-level domain, e.g., `http://example.com/child-site1/`, `http://example.com/child-site2/`, etc.

If your Multisite Network is running with Sub-Directories, you only have a single domain that needs to be connected to the CDN (the top-level domain). However, you can still take advantage of [Domain Sharding](http://cometcache.com/r/domain-sharding/) and define multiple CDN domain names (an advanced configuration that requires configuring CNAMEs through your web hosting company).

### Option 1: Single CDN Domain Name

![static-cdn-filters-single-cdn-domain-name](https://cloud.githubusercontent.com/assets/53005/7761586/717a62f8-fff5-11e4-834b-d374d5871755.png)

### Option 2: Multiple CDN Domain Names

When you're running a WordPress Multisite Network in sub-directory mode, the only reason you would configure multiple CDN domain names is to take advantage of [Domain Sharding](http://cometcache.com/r/domain-sharding/).

![static-cdn-filters-multiple-cdn-domain-names](https://cloud.githubusercontent.com/assets/53005/8264042/75f5d27e-16af-11e5-8f29-2d28c1bf1b77.png)

Domain Sharing allows you distribute your static resources to multiple CDN domain names, thereby increasing performance by working around concurrency limits in popular browsers; i.e., making it possible for browsers to download many more resources simultaneously, resulting in a faster overall completion time. 

## WordPress Multisite w/ Sub-Domains

If you are running a WordPress Multisite Network with Sub-Domains (i.e., your child sites all have their own sub-domain address like `child1.example.com`, `child2.example.com`, etc.), you can define a list of sub-domains with their corresponding CDN hostname to map a specific CDN hostname to that sub-domain. Comet Cache will then use the respective CDN hostname when rewriting static resource URLs on that sub-domain.

If you only want to enable the Static CDN Filters for the primary domain (e.g., `example.com`), then you can simply specify a primary domain CDN mapping and skip the sub-domain mappings.

![static-cdn-filters-sub-domains](https://cloud.githubusercontent.com/assets/53005/8264056/a9718da0-16af-11e5-8ebd-676a8d7939b5.png)


## WordPress Multisite w/ Domain Mapping

If you're using Domain Mapping (i.e., your sub-domain sites are mapped to their own top-level domains, such as `example1.com`, `example2.com`, etc.) and you want to enable Static CDN Filters on the mapped domains, simply supply a list of mapped domains with their corresponding CDN hostname.

If you only want to enable the Static CDN Filters for the primary domain (e.g., `example.com`), then you can simply specify a primary domain CDN mapping and skip the sub-domain mappings.

![static-cdn-filters-domain-mapping](https://cloud.githubusercontent.com/assets/53005/8264050/9f5b184a-16af-11e5-96f2-70db939e8eac.png)
