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
---

A Linux application written using PyQt5 to play white noise (or other ambient sounds) in the background.

Supports layering multiple sounds over one another. Sounds automatically loop indefinitely.

{% include gallery %}

## Download

<div class="download-button">
<a href="https://github.com/ryangwsimmons/WhiteNoiseLinux/releases/latest" class="btn btn--primary" id="deb-download">Ubuntu/Debian</a>
<a href="https://github.com/ryangwsimmons/WhiteNoiseLinux/releases/latest" class="btn btn--primary" id="rpm-download">Fedora/OpenSUSE</a>
<a href="https://github.com/ryangwsimmons/WhiteNoiseLinux/releases/latest" class="btn btn--primary" id="arch-download">Arch/Manjaro</a>
</div>

## Installation

### Ubuntu/Debian
1. Download the `.deb` file using the button above.
2. Open a terminal in the folder the file downloaded to.
3. Run the following command:

```shell
sudo apt install ./WhiteNoiseLinux.deb
```

### Fedora/OpenSUSE
1. Download the `.rpm` file using the button above.
2. Open a terminal in the folder the file downloaded to
3. Run the following command:

#### Fedora
```shell
sudo dnf install ./WhiteNoiseLinux.rpm
```

#### OpenSUSE
```shell
sudo zypper install ./WhiteNoiseLinux.rpm
```

### Arch/Manjaro
1. Download the `.pkg.tar.xz` file using the button above.
2. Open a terminal in the folder the file downloaded to.
3. Run the following command:

```shell
sudo pacman -U ./WhiteNoiseLinux.pkg.tar.xz
```

{% include get-download-script extension="deb,rpm,pkg.tar.xz" id="deb-download,rpm-download,arch-download" reponame="whitenoiselinux" %}
