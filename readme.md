# install

- try run untouched `docker-compose.dev.yaml/docker-compose.yaml` first(check if the domain is working correctly)
- if it's served alright, try uncomment all the settings with `web-secure`. check if letsencrypt log created inside `./letsencrypt`.
- change letsencrypt url to real from staging url.
- do the setting and install. download `LocalSettings.php` files from browser, place it inside workspace directory.
- add extension setting to `LocalSettings.php`. check *setting extensions* for more detail.
- uncomment `LocalSettings.php` from `docker-compose.yaml`.
- reset all the service.

# troubleshooting

- create `./letsencrypt` directory if it's not available
- chrome no longer accepts insecure request from browser. any domains other than `localhost` would be blocked from the browser; when troubleshoot, try commenting/uncommenting `web-secure(https)` settings from `.deploy.labels`.

# setting extensions

Add the following code at the bottom of your LocalSettings.php:
```php
wfLoadExtension( 'SyntaxHighlight_GeSHi' );
wfLoadExtension( 'MathJax' );
# ----- Mathjax
# Change default font size (default: 100)
#$wgMjSize = 100;
# Use local MathJax installation (default: false, use CDN)
#$wgMjUseCDN = true;
```