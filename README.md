<p align="left">
<a href="#"><img title="Made in INDIA" src="https://img.shields.io/badge/MADE%20IN-INDIA-green?colorA=%23ff9933&colorB=%23017e40&style=for-the-badge"></a>
</p>

<p align="center">
<a href="#"><img title="" src="#" width='500'></a> 

<p align='center' style="font-size:48px; font-family: cursive; "> XSS Hunter Express </p>
</p>

<p align="center">
<a href="https://github.com/Pruthviraj-S"><img title="Author" src="https://img.shields.io/badge/Author-Pruthviraj--S-red.svg?logo=github"></a>
<a href="/LICENSE"><img title="License" src="https://img.shields.io/github/license/Pruthviraj-S/xsshunter"></a>
<a href="#"><img title="Author" src="https://img.shields.io/badge/Version-v0.6-green.svg"></a>
</p>

## Setup

### Requirements
* `docker` and `docker-compose` installed
* Host with at least 2 GB of RAM
* A hostname (e.g. `host.example.com`) which you can map to your server's IP (have DNS control for)
* *[For Email Notifications]* To receive email notifications of XSS payload fires you'll need an email account with valid SMTP credentials. You can use many regular email accounts like Gmail for this purpose. This is not required if you don't want email notifications.

### Configuring Your Instance
To set up XSS Hunter Express, modify the [`docker-compose.yaml`](https://github.com/mandatoryprogrammer/xsshunter-express/blob/main/docker-compose.yml) file with your appropriate settings/passwords/etc.

The following are some YAML fields (in [`docker-compose.yaml`](https://github.com/mandatoryprogrammer/xsshunter-express/blob/main/docker-compose.yml)) you'll need to modify before starting the service:

* `HOSTNAME`: Set this field to your hostname you want to use for your payloads and to access the web admin panel. Often this is as short as possible (e.g. `xss.ht`) so the payload can be fit into various fields for testing. This hostname should be mapped to the IP address of your instance (via a DNS `A` record).
* `SSL_CONTACT_EMAIL`: In order to automatically set up and renew TLS/SSL certificates via [Let's Encrypt](https://letsencrypt.org/) you'll need to provide an email address.

The following are needed if you want email notifications:

* `SMTP_EMAIL_NOTIFICATIONS_ENABLED`: Leave enabled to receive email notifications (you must set this up via the below configurations as well).
*  `SMTP_HOST`: The host of your SMTP server where your email account is hosted (e.g. `smtp.gmail.com`).
* `SMTP_PORT`: The port of your SMTP server (e.g. `465`).
* `SMTP_USE_TLS`: Utilize TLS if your SMTP server supports it.
* `SMTP_USERNAME`: The username of the email account on your SMTP server (e.g. `exampleuser`).
* `SMTP_PASSWORD`: The password of the email account on your SMTP server (e.g. `Password1!`).
* `SMTP_FROM_EMAIL`: The email address of your email account on the SMTP server (e.g. `exampleuser@gmail.com`).
* `SMTP_RECEIVER_EMAIL`: What email the notifications will be sent to. This may be the same as the above but could be different.

Finally, the following is worth considering for the security conscious:

* `CONTROL_PANEL_ENABLED`: If you want to minimize the attack surface of your instance you can disable the web control panel. This makes it so you'll only receive emails of payload fires (results will still be stored on disk and in the database).


### Build & Start XSS Hunter Express

Once you've set it up, simply run the following commands to set up the service:

```bash
# Change into the repo directory
cd xsshunter-express/
# Start up postgres in the background
docker-compose up -d postgresdb
# Start up the service
docker-compose up xsshunterexpress
```



## Features
* Everything from original version +
    * switch for lets encrypt ssl generation

## Screenshots

![](images/payload-fires.png)
![](images/collected-pages.png)
![](images/settings.png)
![](images/xss-payloads.png)

## Credits

* The front-end is built in Vue and utilizes the [`vue-black-dashboard`](https://github.com/creativetimofficial/vue-black-dashboard) framework. Licensed under MIT (see [https://github.com/creativetimofficial/vue-black-dashboard#licensing](https://github.com/creativetimofficial/vue-black-dashboard#licensing)).

* Credits to [mandatoryprogrammer](https://github.com/mandatoryprogrammer) and other contributors for creating the original version.

## Disclaimer
Contents of this repository are only for my personal use and refrence. If you want to use the code or have any concern with the modifications, please contact me.
## Contact
<p align='left'><a href='https://discord.com/channels/@me/495023063486824467'><img alt="Discord" src="https://img.shields.io/badge/Discord%20-%237289DA.svg?&style=for-the-badge&logo=discord&logoColor=white"/></a></p>