---
title: WhiteNoiseLinux
excerpt: A Linux application to play white noise in the background.
header:
  teaser: /assets/images/whitenoiselinux/icon.svg
gallery:
  - url: /assets/images/whitenoiselinux/main.png
    image_path: assets/images/whitenoiselinux/main.png
    alt: WhiteNoiseLinux main screen
  - url: /assets/images/whitenoiselinux/about.png
    image_path: assets/images/whitenoiselinux/about.png
    alt: WhiteNoiseLinux about window
project_order: 1
---

A Linux application that plays white noise (and other ambient sound) audio files in the background.

Supports layering multiple sounds over one another. Sounds automatically loop indefinitely.


{% include gallery %}

## Installation

### Distro Packages (Recommended)

Use the latest provided package for your distro, available from the [OpenSUSE Build Service](https://software.opensuse.org//download.html?project=home%3Aryangwsimmons%3AWhiteNoiseLinux&package=whitenoiselinux). Click the link, select your distro, and follow the instructions for adding the repository and installing manually. Unless you know what you're doing, don't just grab the binary packages, or else you won't get updates.

### AppImage

AppImages are also available from the GitHub [releases page](https://github.com/ryangwsimmons/WhiteNoiseLinux/releases). If your distro is not listed on the page at the OpenSUSE build service, this is the best option for using the application. To run the AppImage:

1. Download the latest `.AppImage` file from the GitHub releases page (linked above).

2. Open a terminal in the location the file downloaded to (usually your Downloads folder) and run the following:

   ```shell
   chmod +x <name_of_file>.AppImage
   ```

   After this, you should be able to run the program by simply opening the `.AppImage` file.

3. (Optional) Add a menu entry for the application using [`appimaged`](https://github.com/probonopd/go-appimage).

## Usage

On first run, the app creates a `.whitenoiselinux` directory in your home directory. Inside this directory, there is another directory called `sounds`.

Inside this directory, place the sounds you want. These sounds must be 2 channel (stereo) Ogg/Vorbis audio files. If an audio file has a title in its metadata, this title will be used instead of the file name in the interface.

To obtain sounds, I'd recommend the following process:

1. Go on YouTube, and search for "white noise".
2. Find a few different sounds you like, and download the audio for them with [youtube-dl](https://youtube-dl.org/).
3. Use [Audacity](https://www.audacityteam.org/) to trim the audio file down to around 2 minutes or so.
4. Export this new, trimmed audio as an Ogg file.
5. During the export process, you will be given the option to enter a "Track Title" for the file. You can enter the name you would like for the sound in this field.
6. Save this audio file in the `~/.whitenoiselinux/sounds` directory.
