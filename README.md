# DEMO SITE SETUP PROCESS
===========================================================================================================

# To activate multisite in WordPress:
1. Open the `wp-config.php` file from the WordPress folder.
2. Add this line above where it says `/* That's all, stop editing! Happy publishing. */`:

```php
define( 'WP_ALLOW_MULTISITE', true );
```
3 . After that go the wordpress admin dashboard->Tools->Network setup and click Install.
