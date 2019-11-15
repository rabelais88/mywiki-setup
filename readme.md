# troubleshooting

- create `letsencrypt/` directory if it's not available
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