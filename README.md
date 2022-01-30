# check-nextcloud
CheckMK local check plugin to check Nextcloud installations

Install it into /usr/lib/check_mk_agent/local/ your Nextcloud Host
```
wget -O /usr/lib/check_mk_agent/local/check-nextcloud https://raw.githubusercontent.com/bashclub/check-nextcloud/main/check-nextcloud
chmod +x /usr/lib/check_mk_agent/local/check-nextcloud
/usr/lib/check_mk_agent/local/check-nextcloud
```

After running once, the script will create the config file `/etc/check_mk/nextcoud.conf` with default settings (JSON Format):
```
{
    "nextcloud.zmb.rocks": {
        "nc_path": "/nextcloud/server",
        "nc_php_version": "7.4",
        "nc_www_user": "www-data"
    }
}
```
Please adjust the settings to your needs.
You can also add multiple instances.

Example config with multiple instances (e.g. on ISPconfig):
```
{
    "nextcloud.zmb.rocks": {
        "nc_path": "/var/www/nextcloud.zmb.rocks",
        "nc_php_version": "7.4",
        "nc_www_user": "web001"
    },
    "nextcloud.bashclub.org": {
        "nc_path": "/var/www/nextcloud.bashclub.org",
        "nc_php_version": "8.0",
        "nc_www_user": "web001"
    }
}
```
