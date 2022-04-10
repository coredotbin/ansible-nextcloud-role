# Ansible Nextcloud Role

[![Ansible Lint](https://github.com/coredotbin/ansible-nextcloud-role/actions/workflows/ansible_lint.yaml/badge.svg)](https://github.com/coredotbin/ansible-nextcloud-role/actions/workflows/ansible_lint.yaml)

**Note:** This is **heavily a WIP** - Please do not expect this to work for you at this time.

This role configures a web server on your host for Nextcloud

## Role configuration
* `domain_name` (default: localdomain) - Your domain for web server configuration. i.e. `example.com` if you would like your Nextcloud instance to be reachable at nextcloud.example.com
* `nextcloud_subdomain` (default: nextcloud) - The subdomain at which you'd like to access your Nextcloud instance
* `nextcloud_ssl` (default: false) - Whether or not you'd like to enable SSL. This will not create certificates, you will need to configure [certbot](https://certbot.eff.org/instructions) or other certificates manually.
* `nextcloud_apache2_virtualhost` (default: false) - Enable this if you would like to use a virtual host configuration rather than directory-based. See the [Nextcloud documentation](https://docs.nextcloud.com/server/latest/admin_manual/installation/source_installation.html#apache-web-server-configuration) for more information.
* `nextcloud_apache2_fcgi` (default: false) - Enable this if you are using `mod_fcgi` rather than the standard `mod_php`. This will enable the `mod_setenvif` PHP module.
* `nextcloud_apache2_config_path` (default: /etc/apache2/sites-available/nextcloud.conf) - The path to your Nextcloud Apache2 site configuration.

### Experimental options
* `nextcloud_nginx` (default: false) - Configure an nginx web server rather than Apache2. **nginx is not officially supported by Nextcloud**
* `nextcloud_nginx_config_path` (default: /etc/nginx/nginx.conf) - The path to your Nextcloud nginx configuration.
* `nextcloud_nginx_ssl_certificate_path` (default: /etc/ssl/nginx/nextcloud.localdomain.crt) - The path to your SSL certificate
* `nextcloud_nginx_ssl_key_path` (default: /etc/ssl/nginx/nextcloud.localdomain.key) - The path to your SSL certificate key
