# Writing Permissions
In order to function correctly, WP Rocket needs be able to create and write to certain files and folders within your WordPress install. The following files and folders are associated with, or written to by WP Rocket:
```bash
 {wordpress root folder}
 ┣━.htaccess
 ┣━wp-config.php
 ┗━wp-content
   ┣━advanced-cache.php
   ┣━cache
   ┃ ┣━busting
   ┃ ┣━critical-css
   ┃ ┣━min
   ┃ ┗━wp-rocket
   ┗━wp-rocket-config
```
### `1. .htaccess`
```bash
 {wordpress root folder}
 ┗━.htaccess
```
    On Apache servers, the .htaccess file needs to be writable for WP Rocket (CHMOD `0644`). After activation there should be a large block of code present from WP Rocket, beginning at the very top of the file:
```bash
 # BEGIN WP Rocket v{version number}

 ... lots of code in here ...

 # END WP Rocket

 ... other code down here

```
### `2. advanced-cache.php`
 ```bash
 ┗━wp-content
  ┗━advanced-cache.php
 ```
    Make sure that advanced-cache.php in the wp-content folder references only WP Rocket (CHMOD `0644`).

## Additional Notes:
 These other important files also needed to be writable in order for WP Rocket to work properly.
 Make sure that WP Rocket has writing permissions for the cache folder (CHMOD `0755`), and that it contains the 4 subfolders depicted below. All of these WP Rocket needs to be able to write to. If these folders don’t exist you should create them manually.

### `1. Cache folder (and subfolders)`
 ```bash
 {wordpress root folder}
┗━wp-content
  ┗━cache
    ┣━busting
    ┣━critical-css
    ┣━min
    ┗━wp-rocket
 ```

### `2. wp-config.php`
```bash
 {wordpress root folder}
 ┗━wp-config.php
```
 The wp-config.php file needs to be writable for WP Rocket (CHMOD 0644). Make sure that the following line is present at the top of wp-config.php, after the opening <?php tag. If it is too far down in the file, WP Rocket will not work!

 ```bash
  define( 'WP_CACHE', true ); // Added by WP Rocket
 ```

 Also, make sure there is no reference to another caching plugin. For example, WP Super Cache leaves this line behind:

 ```bash
 define( 'WPCACHEHOME', '{/path/to/wordpress/root/}wp-content/plugins/wp-super-cache/' ); //Added by WP-Cache Manager
 ```

### `3. WP Rocket configuration folder`
 ```bash
 {wordpress root folder}
 ┗━wp-content
    ┗━wp-rocket-config
 ```