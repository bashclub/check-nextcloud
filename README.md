# check_nextcloud
CheckMK local check plugin to check Nextcloud installations

Install it into /usr/lib/check_mk_agent/local/ your Nextcloud Host
```
wget -O /usr/lib/check_mk_agent/local/check_nextcloud https://raw.githubusercontent.com/bashclub/check_nextcloud/main/check_nextcloud
chmod +X /usr/lib/check_mk_agent/local/check_nextcloud
/usr/lib/check_mk_agent/local/check_nextcloud
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
