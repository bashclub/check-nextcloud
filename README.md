# check-nextcloud
CheckMK local check plugin to check Nextcloud installations.
Multiple instances or checks inside docker containers are supported.

Install it into /usr/lib/check_mk_agent/local/ your Nextcloud Host
```
interval=3600
mkdir -p /usr/lib/check_mk_agent/local/$interval
wget -O /usr/lib/check_mk_agent/local/$interval/check-nextcloud https://raw.githubusercontent.com/bashclub/check-nextcloud/main/check-nextcloud
chmod +x /usr/lib/check_mk_agent/local/$interval/check-nextcloud
/usr/lib/check_mk_agent/local/$interval/check-nextcloud
```

After running once, the script will create the config file `/etc/check_mk/nextcloud.conf` with default settings (JSON Format):
```
{
    "nextcloud.zmb.rocks": {
        "nc_path": "/nextcloud/server",
        "nc_php_version": "7.4",
        "nc_www_user": "www-data"
    }
}
```


### Multiple instances example
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
### Docker example:
```
{
    "nextcloud.zmb.rocks": {
        "nc_path": "/var/www/html",
        "nc_php_version": "",
        "nc_www_user": "www-data",
        "docker_container": "composestack-nextcloud-fpm"
    }
}
```

 Author
### Thorsten Spille
[<img src="https://storage.ko-fi.com/cdn/brandasset/kofi_s_tag_dark.png" rel="Support me on Ko-Fi">](https://ko-fi.com/thorakel)
