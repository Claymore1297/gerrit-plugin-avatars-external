External URL Avatar Plugin Configuration
=========================

This plugin allows to use an own web service to load the avatar images from.

Options:

* `avatar.url` - the location of avatar images containing `${user}`, which will then be replaced by the `username`. Required.
* `avatar.changeUrl` - the URL shown in Gerrit's user settings to tell the user, where the avatar can be changed. Optional.
* `avatar.sizeParameter` - URL parameter with `${size}` placeholder to
  forward the preferred image size to the avatar provider. Optional.
* `avatar.lowerCase`  - Convert the username and email to lower case.
  Default value = false. Optional.

Example (to be added to `etc/gerrit.config`):

    [avatar]
        url = http://example.org/avatars/${user}.jpg
        changeUrl = http://example.org/account.html
        sizeParameter = s=${size}x${size}
        lowerCase = true

Please note that `http://` URLs will be automatically rewritten to `https://`, if `gerrit.canonicalWebUrl` uses HTTPS.
