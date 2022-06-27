**Gute rsnapshot Erläuterungen und tiefgehendere Einrichtung**

- [https://wiki.ubuntuusers.de/rsnapshot/](https://wiki.ubuntuusers.de/rsnapshot/)

**WP CLI Dokumentation**

- [https://wp-cli.org/de/](https://wp-cli.org/de/)
- [https://developer.wordpress.org/cli/commands/](https://developer.wordpress.org/cli/commands/)

**Cachify**

- [Website](https://cachify.pluginkollektiv.org/de/)
- [Dokumentation](https://cachify.pluginkollektiv.org/de/documentation/)






## Admin Zugriff auf IP Adressen beschränken

    function page_ip_restriction() {
        if( current_user_can('edit_others_pages') )
        {
            // Whitelist
            $whitelist = array(
                '127.0.0.1',
                '127.0.0.2',
                '145.253.118.26',
            );

            // Check if current user IP is out of the whitelist, then redirect to home
            if(!in_array($_SERVER['REMOTE_ADDR'], $whitelist)) {
            wp_logout();
                wp_redirect(home_url(), 403); // 403 -> Forbiden access
                exit();
            }
        }
    }
    add_action('admin_init', 'page_ip_restriction', 10);