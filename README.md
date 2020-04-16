
# WP Custom Plugin Manager
A custom handler class to manage your plugins plugins from within your plugin, theme or any other code.

What you can do with it:
- Programmatically **Install** and **Uninstall** plugins
- Programmatically **Activate** and **Deactivate** plugins
- Programmatically **Upgrade** plugins

  

### How it works
To make it work, please make sure you initiate the `wp-custom-plugin-updater-skin.php` file, as well as the `includes` folder.
Once you loaded the files, you can start using it as followed.

### Initiate the handler

    //Include the files mentioned above
    include( 'wp-custom-plugin-manager.php' );
    
    $plugin_slug =  'wp-webhooks-comments/wp-webhooks-comments.php'; // usually it is the plugin_folder/plugin_file.php
    $plugin_download =  'https://downloads.wordpress.org/plugin/wp-webhooks-comments.latest-stable.zip'; //The zip file of your plugin version you want to install
    $manager =  new  WP_Custom_Plugin_Updater(); //Init our handler class

Once you initiated everything, you can use the following functions to simply manage your plugin

### Install a plugin

    $manager->install( $plugin_slug, $plugin_download, array( 'prevent_outputs' => true ) );

### Activate a plugin

    $manager->activate( $plugin_slug );

### Deactivate a plugin

    $manager->deactivate( $plugin_slug );

### Update a plugin
//Works only for WordPress.org-hosted plugins or plugins who use a plugin update class like Easy Digital Downloads

    $manager->update( $plugin_slug, array( 'prevent_outputs'  =>  true ) );

### Uninstall (delete) a plugin

    $manager->uninstall( $plugin_slug, array( 'force_delete'  =>  true ) ); //Force delete also deletes the plugin in case its active
