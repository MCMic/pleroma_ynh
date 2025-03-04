<!--
N.B.: This README was automatically generated by https://github.com/YunoHost/apps/tree/master/tools/README-generator
It shall NOT be edited by hand.
-->

# Pleroma for YunoHost

[![Integration level](https://dash.yunohost.org/integration/pleroma.svg)](https://dash.yunohost.org/appci/app/pleroma) ![Working status](https://ci-apps.yunohost.org/ci/badges/pleroma.status.svg) ![Maintenance status](https://ci-apps.yunohost.org/ci/badges/pleroma.maintain.svg)

[![Install Pleroma with YunoHost](https://install-app.yunohost.org/install-with-yunohost.svg)](https://install-app.yunohost.org/?app=pleroma)

*[Lire ce readme en français.](./README_fr.md)*

> *This package allows you to install Pleroma quickly and simply on a YunoHost server.
If you don't have YunoHost, please consult [the guide](https://yunohost.org/#/install) to learn how to install it.*

## Overview

Pleroma is a microblogging server software that can federate (= exchange messages with) other servers that support ActivityPub. What that means is that you can host a server for yourself or your friends and stay in control of your online identity, but still exchange messages with people on larger servers. Pleroma will federate with all servers that implement ActivityPub, like Friendica, GNU Social, Hubzilla, Mastodon, Misskey, Peertube, and Pixelfed.

For user friendly details about Pleroma: [see here](https://blog.soykaf.com/post/what-is-pleroma/)

**Mastodon web front-end for Pleroma:** Add **/web** in front of your Pleroma domain, eg. pleroma.domain.tld/web


**Shipped version:** 2.5.0~ynh1

**Demo:** http://distsn.org/pleroma-instances.html

## Screenshots

![Screenshot of Pleroma](./doc/screenshots/screenshot1.png)

## Disclaimers / important information

## Limitations

- **Pleroma** require a dedicated **root domain**, eg. pleroma.domain.tld
- **Pleroma** require a valid **certificate** installed on the domain. Yunohost can **install Letsencrypt certificate** on the domain from **admin web-interface** or through **command-line**.
- This package is currently set to **single-instance** that means you can run a **single Pleroma instance** on a **single server**.
- The admin **password** entered when installing must **not** contain **special characters**. (See [issue #132](https://github.com/YunoHost-Apps/pleroma_ynh/issues/132))
- LDAP supported but HTTP auth not.

## Admin Tasks
Go to **cd /var/www/pleroma/live**.

### Adding users

**Run:**

    $ ( cd /var/www/pleroma/live && sudo -u pleroma MIX_ENV=prod ./bin/pleroma_ctl user new <NICKNAME> <EMAIL> )

### Password reset

**Run:** 

    $ ( cd /var/www/pleroma/live && sudo -u pleroma MIX_ENV=prod ./bin/pleroma_ctl user reset_password <NICKNAME> )

This will generate a **password reset link** that you can then send to the user.

### Moderators

You can make users **moderators**. They will then be able to **delete any post**.

**Run:**

    $ ( cd /var/www/pleroma/live && sudo -u pleroma MIX_ENV=prod ./bin/pleroma_ctl user set <NICKNAME> --[no-]admin )

**--admin** option will **make the user moderator** and **--no-admin** will **take away the moderator privileges** from the user.

## Documentation and resources

* Official app website: <https://pleroma.social/>
* Official admin documentation: <https://docs.pleroma.social/>
* Upstream app code repository: <https://git.pleroma.social/pleroma/pleroma/>
* YunoHost documentation for this app: <https://yunohost.org/app_pleroma>
* Report a bug: <https://github.com/YunoHost-Apps/pleroma_ynh/issues>

## Developer info

Please send your pull request to the [testing branch](https://github.com/YunoHost-Apps/pleroma_ynh/tree/testing).

To try the testing branch, please proceed like that.

``` bash
sudo yunohost app install https://github.com/YunoHost-Apps/pleroma_ynh/tree/testing --debug
or
sudo yunohost app upgrade pleroma -u https://github.com/YunoHost-Apps/pleroma_ynh/tree/testing --debug
```

**More info regarding app packaging:** <https://yunohost.org/packaging_apps>
