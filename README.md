# PIXEL Web Services

The [PIXEL Web software](http://ledpixelart.com/raspberry-pi/) for the Raspberry Pi is a fantastic way to control the [PIXEL LED Art frame](http://ledpixelart.com/) from the web. By default, this software does not operate on a Raspberry Pi in headless mode and cannot start up on its own when the Pi is rebooted. These service scripts help overcome that limitation to make the PIXEL Web software truly hands off.

## Configure the Pi

On a fresh installation of Raspbian, the Pi boots to the terminal. For these service scripts to operate properly, the Pi must boot and automatically log into the Desktop interface.

```text
NOTE: Following these instructions causes the Raspberry Pi to bypass
the login prompt on start up. These steps should not be followed in an
environment where security is a priority. Exercise extreme caution
and consider the ramifications prior to proceeding.
```

1. In a terminal, run: `sudo raspi-config`

1. Select the `Boot Options` item

1. Select the `Desktop / CLI` item

1. Select `Desktop Autologin`

1. Reboot the Pi when prompted

## Install the Scripts & Supporting Software

The Raspbian operating system will use the scripts correctly whenever they are moved to the appropriate locations.

1. Move the `pixel.desktop` file to `/home/pi/.config/autostart/pixel.desktop`, creating the parent directories as needed

1. The JAR and shell script may be moved to any location which is convinent for you

1. The desktop script used above works very reliably with the XTERM terminal, which is not installed by default. Install it by running: `sudo apt-get -y install xterm`.

## Configure the Scripts

The scripts include a basic set of default configurations which require modification before use.

1. Open `pixel.desktop` and point the reference to the shell script to the fully qualified path for `run.sh`

1. Open `run.sh` and adjust the path to `pixel.jar` to use the correct, fully qualified path

1. Ensure the matrix type, corresponding to `-m` option in `run.sh`, is correct for your configuration per [this guide from Adafruit](https://learn.adafruit.com/web-enabled-pixel-on-raspberry-pi/usage#command-line-switches)

1. Ensure `run.sh` has execute permissions: `chmod +x run.sh`

## Finalizing the Install

All of the scripts are in place and ready for use.

1. Reboot the Pi

1. After the start up is complete, observe the PIXEL interface by going to http://pi-ip-address/ in a web browser

1. (Optional) Consider using [Dataplicity](https://dataplicity.com/) to access the PIXEL over the internet