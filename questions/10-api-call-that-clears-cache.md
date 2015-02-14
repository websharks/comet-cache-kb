---
title: Is there an API call that clears the cache?
categories: questions
tags: clearing-the-cache
author: jaswsinc
github-issue: https://github.com/websharks/zencache-kb/issues/10
---
**Question:** Is there an API call that clears the cache?

**Answer:** Yes, ZenCache exposes an API method that makes this possible.

Here is a quick example of how to handle this in PHP code.

```php
<?php
zencache::clear();
```

**TIP:** If you want to make it possible to call this remotely, you might put together a [Must-Use](http://codex.wordpress.org/Must_Use_Plugins) plugin in WordPress, where the MU plugin is just one file that exposes this functionality.

Create the following directory and file:
`/wp-content/mu-plugins/zc-clear.php`

```php
<?php
add_action('init', function()
{
    if(!empty($_GET['zc_clear']) && $_GET['zc_clear'] === 'my-secret-key')
     { zencache::clear(); exit('cache cleared'); }
});
```

Now you would be able to call upon the ZenCache API remotely by including your secret key.
`http://example.com/?zc_clear=my-secret-key`