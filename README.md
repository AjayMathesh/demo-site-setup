# DEMO SITE SETUP PROCESS
====================================================================
# cPanel setup:
1. Login to cPanel with Credentials

2. Go to file manager -> public_html

3. Go to mysql databases menu under databases section

4. Create new database by typing new name and create it.

5. Scroll down and create a database user 

6. Assign a created user to the created database.

7. Set user privileges by giving all privileges

8. Download WordPress from wordpress.org

9. Paste and extract the WordPress zip file in the respected folder (which points your demo site domain URL)

10. Setup and install the WordPress site by accessing the endpoint of the domain in cPanel

11. Give the Database credentials (Database name and password) which you have created through cPanel (Steps 3, 4).

---

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
7. To create new sub-site go to My Sites->Network Admin-> Add New site

---
# Plugin installations and customization process

1. Go to My Sites -> Network Admin -> Plugins

2. Install the plugins such as multisite-cloner, flycart-demo-promotion, create-demo sub site, disable emails, and activate them

3. The demo site should be handled by 2 sites. One is the main site, and another one is a subsite (If you have only a main site, create a subsite by going to My Sites -> Network Admin -> Add New Site).

4. Go to Appearance -> Theme, and install the Storefront theme and storefront child theme.

5. Activate the storefront child theme on the main site and the storefront theme on the subsite.

6. Go to the `wp-content` folder and edit the file `storefront-child-theme/header.php` with the below content to design a header.

7. After that, install the AAM plugin on the network: https://wordpress.org/plugins/advanced-access-manager/.  
   The AAM plugin will help manage user roles and user-specific access.

8. Go to the main site and follow the steps below:

9. Go to the settings page of the AAM plugin.

![aam](https://github.com/user-attachments/assets/7edcf03c-8018-459e-a089-000792279bc2)


10. Add a new user role called "superadmin."

![image](https://github.com/user-attachments/assets/bbf925fd-28d0-40ef-a835-f076807b4491)
![image](https://github.com/user-attachments/assets/752d92f4-ede8-4b0a-a0fa-79fff5f7456a)


11. After adding a superadmin role, assign the superadmin role to the admin who manages this demo site.

12. Capabilities-
These capabilities should be removed to restrict the admin role's access to sensitive settings and features:

- `moderate_comments` - Restrict this capability to prevent users from moderating or managing site comments.
- `manage_categories` - Restrict this capability to prevent users from adding, editing, or managing categories for posts.
- `manage_links` - Restrict this capability to prevent users from managing site links.
- `unfiltered_html` - Restrict this capability to prevent users from posting unfiltered HTML (only allow for super admins).
- `edit_files` - Restrict this capability to prevent users from editing files in the file library.
- `edit_theme_options` - Restrict this capability to prevent users from editing theme options and settings.
- `export` - Restrict this capability to prevent users from exporting site content.
- `publish_posts` - Restrict this capability to prevent users from publishing posts.
- `read` - Restrict this capability to control basic access and viewing permissions on the site.
- `delete_others_pages` - Restrict this capability to prevent users from deleting pages created by others.
- `delete_others_posts` - Restrict this capability to prevent users from deleting posts created by others.
- `delete_pages` - Restrict this capability to prevent users from deleting pages.
- `delete_posts` - Restrict this capability to prevent users from deleting posts.
- `delete_private_pages` - Restrict this capability to prevent users from deleting private pages.
- `delete_private_posts` - Restrict this capability to prevent users from deleting private posts.
- `delete_published_pages` - Restrict this capability to prevent users from deleting published pages.
- `delete_published_posts` - Restrict this capability to prevent users from deleting published posts.
- `edit_others_pages` - Restrict this capability to prevent users from editing pages created by others.
- `edit_others_posts` - Restrict this capability to prevent users from editing posts created by others.
- `edit_pages` - Restrict this capability to prevent users from editing pages.
- `edit_posts` - Restrict this capability to prevent users from editing posts.
- `edit_private_pages` - Restrict this capability to prevent users from editing private pages.
- `edit_private_posts` - Restrict this capability to prevent users from editing private posts.
- `edit_published_pages` - Restrict this capability to prevent users from editing published pages.
- `edit_published_posts` - Restrict this capability to prevent users from editing published posts.
- `publish_pages` - Restrict this capability to prevent users from publishing pages.
- `read_private_pages` - Restrict this capability to prevent users from reading private pages.
- `read_private_posts` - Restrict this capability to prevent users from reading private posts.

![Capability Restriction Example](https://github.com/user-attachments/assets/930755c9-f9eb-4375-9aa0-9148a8b9e14e)

**Note**: Restrictions are applied to the admin role because all demo site visitors are automatically logged in as admins. This ensures that certain elements remain hidden.

13. Go to Pages and create a new page (Home page) and set this page as a static page in WordPress settings.

14. Paste the shortcode below on that page:

    ```
    [cds_register]
    ```
    This shortcode will verify the Recaptcha process automatically.

15. Go to My Sites -> Network Admin -> Multisite Cloner in the admin dashboard and check whether the URL of a site is correctly projected to the subsite that needs to be cloned.
For Eg:- Screenshot of WPBundle Demo site

![image](https://github.com/user-attachments/assets/3813077e-baaf-42da-8439-46bdc0836359)

---

For understanding:  

- **Main site** - Acts as an entry point, performs Recaptcha verification, and redirects to the subsite by creating a new demo instance.

- **Sub site** - All demo work should be done here. This is the site that will be watched by the users.

After completing all the steps, verify that everything is functioning correctly by accessing the endpoint.


