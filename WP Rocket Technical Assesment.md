Issue:

A customer installed WP Rocket on a server where they have their own caching system. The host has disabled WP Rocket's cache programmatically. The rest of the features are enabled.

The host also sets strict permissions on files. This results in several warnings being triggered about the following WP Rocket files not being writeable:
advanced-cache.php
.htaccess

Since page caching is disabled, this doesn't prevent WP Rocket from working.

Write a helper plugin that will prevent these notices from being displayed.

Hints
You can see WP Rocket's code on GitHub: https://github.com/wp-media/wp-rocket/
WP Rocket uses the standard WordPress hooks to display admin notifications.
