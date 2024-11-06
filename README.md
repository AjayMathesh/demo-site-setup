# DEMO SITE SETUP PROCESS
===========================================================================================================
# cPanel setup for Multisite
1. Login to cPanel with Credentials
2. Go to file manager -> public_html
3. Create a folder with plugin slug.
4. create new database by typing new name and create it.
6. Scroll down and create a database user 
7. Assign a created user to the created database.
8. set user privileges by giving all privileges
9. Download Wordpress from wordpress.org
10. Paste and extract the WordPress zip file in the above created folder(step 3)

# To activate multisite in WordPress:
1. Open the `wp-config.php` file from the WordPress folder.
2. Add this line above where it says `/* That's all, stop editing! Happy publishing. */`:

    ```php
    define( 'WP_ALLOW_MULTISITE', true );
    ```

3. After that, go to the WordPress admin dashboard -> Tools -> Network setup and click Install.
4. After clicking Install, it will display two code blocks which need to be pasted in `wp-config.php` and `.htaccess` files respectively.
5. Paste those codes carefully by reading the instructions.
6. After all this process you can see the My sites Menu on the top left of the admin dashbaord, where you can manage your multisite network.
   For Eg:-
   https://i0.wp.com/wordpress.org/support/files/2018/11/network-admin-link.png?fit=383%2C184&ssl=1

   


