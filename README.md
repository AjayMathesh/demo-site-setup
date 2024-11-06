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

12. Restrict permissions and hide the necessary menus for the admin role.

![image](https://github.com/user-attachments/assets/d60fdf8f-10a8-40fb-b858-b073c54c7fac)


    Why are we restricting for admin roles?

    Because anybody who visits the demo site will be logged in as an admin, so we are hiding certain elements.

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


