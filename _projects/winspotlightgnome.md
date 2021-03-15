---
title: WinSpotlightGNOME
excerpt: A utility for automatically setting the Bing image of the day as your desktop background in GNOME.
header:
  teaser: /assets/images/winspotlightgnome/icon.svg
---

A utility for automatically downloading the Bing photo of the day, and setting it as your desktop background in GNOME. The name comes from the fact that this utility originally downloaded Windows Spotlight images, however the API for that service is private, and the endpoint appears to have changed, so unfortunately it is no longer possible for me to fetch images from that source.

This project is specifically for Linux systems using systemd and running GNOME, such as Ubuntu, Manjaro GNOME, or Fedora Workstation. However, with a little work, it could easily be modified to work with other desktop environments, or with an alternative to systemd timers such as cron.

## Download

<div class="download-button">
<a href="https://github.com/ryangwsimmons/WinSpotlightGNOME/releases/latest" class="btn btn--primary" id="deb-download">Ubuntu/Debian</a>
</div>

## Installation

### Using the Debian Package (Recommended)
If you're on Debian, Ubuntu, or any of their derivates, you can use the provided Debian package to install the utility:
1. Download the `.deb` file using the button above.
2. Open a terminal in the folder the file was downloaded to.
3. Run the following commands:

```shell
sudo apt install ./filename.deb
systemctl --user daemon-reload
systemctl --user enable winspotlightgnome.timer
systemctl --user start winspotlightgnome.timer
```
Replacing `filename.deb` with the name of the file that you downloaded.

### Installing Manually

#### Dependencies
- Bash or Zsh (may work with other shells, but this is untested).
- [cURL](https://curl.haxx.se/)
- [Jq](https://stedolan.github.io/jq/)

1. Clone or download the utility's Git repo (requires [Git](https://git-scm.com/) to be installed):
    ```shell
    git clone https://github.com/ryangwsimmons/WinSpotlightGNOME.git
    ```
2. Open a terminal and `cd` into the repo folder that you downloaded.
3. Make the `winspotlightgnome` script executable:
    ```
    chmod +x winspotlightgnome
    ```
4. Copy the `winspotlightgnome` script to the `opt` folder on your system:
    ```
    sudo cp winspotlightgnome /opt/
    ```
5. Copy the WinSpotlightGNOME `.service` and `.timer` files to the systemd user unit directory:
    ```
    sudo cp winspotlightgnome.service winspotlightgnome.timer /usr/lib/systemd/user/
    ```
6. Reload the systemd user daemon:
    ```
    systemctl --user daemon-reload
    ```
7. Enable and start the WinSpotlightgnome systemd timer
    ```
    systemctl --user enable winspotlightgnome.timer
    systemctl --user start winspotlightgnome.timer
    ```

## Configuration
The following options can be changed by modifying the `winspotlightgnome` script, changing the various variables at the top of the file:

### **locale**
An option sent to the Bing API to determine which photos are downloaded. If desired, you should change this to your current locale (i.e. en-US, en-CA, etc.).

### **imgPath**
The path where images downloaded by the utility will be stored.

### **deleteImagesAfterNumDays**
When the utility runs, all images as old or older than the number of days specified here will be deleted from the directory specified previously. If the value specified is less than or equal to 0, images will be preserved indefinitely.

### **setDesktop**
If set to yes, the desktop background will be changed when the utility downloads a new image.

## Updates
To update the utility:

If you installed using the Debian package, just install the updated Debian package using the same procedure outlined above.

If you installed manually, replace all of the files that have changed since the last version (or just replace them all, much easier) and run the following commands:

```
systemctl --user daemon-reload
systemctl --user reenable winspotlightgnome.timer
```

{% include get-download-script extension="deb" id="deb-download" reponame="winspotlightgnome" %}
