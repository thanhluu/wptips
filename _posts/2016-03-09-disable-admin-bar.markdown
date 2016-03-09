---
layout: post
title:  "Disable Admin Bar"
date:   2016-03-09 22:46:41 +0700
categories: wordpress tips
---

In this article, I will show you a simple code snippet to disable WordPress admin bar:

## Disable admin bar for all users except for admin

Paste this code in your theme’s functions.php file:
{% highlight php %}
add_action('after_setup_theme', 'remove_admin_bar');
function remove_admin_bar() {
if (!current_user_can('administrator') && !is_admin()) {
  show_admin_bar(false);
}
}
{% endhighlight %}

## Disable admin bar for all users

If you want to disable it for all users, then simply put use this code in your theme’s functions.php file:
{% highlight php %}
show_admin_bar(false);
{% endhighlight %}
