# PIXEL Web Services

The [PIXEL Web software](http://ledpixelart.com/raspberry-pi/) for the Raspberry Pi is a fantastic way to control the [PIXEL LED Art frame](http://ledpixelart.com/) from the web. By default, this software does not operate on a Raspberry Pi in headless mode and cannot start up on its own when the Pi is rebooted. This service scripts help overcome that limitation to make the PIXEL Web software truly hands off.

## Configure the Pi

On a fresh installation of Raspbian, the Pi boots to the terminal. For these service scripts to operate properly, the Pi must boot and automatically log into the Desktop interface.

```text
NOTE: Following these instructions causes the Raspberry Pi to bypass
the login prompt on start up. These steps should not followed in an
environment where security is a priority. Exercise extreme caution
and consider the ramifications prior to proceeding.
```

1. In a terminal, run: `sudo raspi-config`

1. Select the `Boot Options` item

1. Select `Desktop Autologin`

## Install the Scripts

The Raspbian operating system will use the scripts correctly whenever they are moved to the appropriate locations.

1. Move the `pixel.desktop` file to `/home/pi/.config/autostart/pixel.desktop`

1. The JAR and shell script may be moved to any location which is convinent for you

## Configure the Scripts

The scripts include default paths to various files and must be properly configured before use.

1. Open `pixel.desktop` and point the reference to the shell script to the fully qualified path for `run.sh`

1. Open `run.sh` and adjust the path to `pixel.jar` to use the correct, fully qualified path

## Finalizing the Install

All of the scripts are in place and ready for use.

1. Reboot the Pi

1. After start up is complete, observe the PIXEL interface by going to http://&lt;pi-ip-address&gt;/ in a web browser

1. (Optional) Consider using [Dataplicity](https://dataplicity.com/) to access the PIXEL over the internet