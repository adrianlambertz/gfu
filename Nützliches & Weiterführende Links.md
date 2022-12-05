**Gute rsnapshot Erläuterungen und tiefgehendere Einrichtung**

- [https://wiki.ubuntuusers.de/rsnapshot/](https://wiki.ubuntuusers.de/rsnapshot/)

**CRONTAB**
- [https://crontab-generator.org/](https://crontab-generator.org/)
- [https://crontab.guru/](https://crontab.guru/)

**WP CLI Dokumentation**

- [https://wp-cli.org/de/](https://wp-cli.org/de/)
- [https://developer.wordpress.org/cli/commands/](https://developer.wordpress.org/cli/commands/)

**Cachify**

- [Website](https://cachify.pluginkollektiv.org/de/)
- [Dokumentation](https://cachify.pluginkollektiv.org/de/documentation/)

**Fontsquirrel**

https://www.fontsquirrel.com/

**Scanner**

- [WPSCAN](https://github.com/wpscanteam/wpscan)



**WP CLI Revisionen**

- [wp revisions](https://www.liquidweb.com/kb/delete-post-revisions-using-wp-cli/)




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
    
    
## Nonce zu wp-login.php hinzufügen
    function add_login_nonce() {
            wp_nonce_field('wp_login_nonce', 'wp_login_nonce_field');
    }
    add_action('lostpassword_form', 'add_login_nonce');



    function validate_lost_password_nonce($true) {

                if( !is_admin() ) {
                    if ( ! isset( $_POST['wp_login_nonce_field'] )  || ! wp_verify_nonce( $_POST['wp_login_nonce_field'], 'wp_login_nonce' ) ) {
                        return new WP_Error('denied', '<strong>ERROR</strong>: Bitte kontaktiere den Serveradministrator.');
                    }
                }
            return $true;

        }
    add_action('allow_password_reset', 'validate_lost_password_nonce');
    
## Fehlerhafte wp-ogin versuche alleine loggen

    function pix_log_failed_auth( $username ) {
        $line = $_SERVER['REMOTE_ADDR'] . ' - - [' . date('d/M/Y:H:i:s O') . '] "' .$_SERVER['REQUEST_METHOD']. ' '.$_SERVER['REQUEST_URI'].' ' .$_SERVER['SERVER_PROTOCOL'].'" ' . http_response_code() . ' - Site: '. get_site_url();
        $line .= "\n";

        error_log( $line, 3, "/var/www/wp-login.log" );
    }
    add_action('wp_login_failed', 'pix_log_failed_auth');
