Technexion Ubuntu 20.04 LTS Image Builder
===========================

## Support Hardware
--------
|Hardware|Baseboard|
|---|---|
|PICO-IMX8M-MINI|PI<br>WIZARD (WIP)|
|EDM-G-IMX8M-PLUS|(WIP)|

****
## Contents
* [Overview](#Overview)
* [Build-Image (for developer)](#Build-Image)
    * Download the source code
    * Compiling Environment Setup
    * Build a runtime Image
    * Flash the image to the target board
* [Quick-Start (for user)](#Quick-Start)
* [Apps-Developing](#Apps-Developing)
* [Known-Issues](#Known-issues)

****
### Overview
-----------
Technexion Ubuntu rootfs(Root Filesystem) was be generated by bash scripts, that help the
users to produce a customized ubuntu image using Cananical unique tool named `debootstrap`,
then adapt QEMU to config custom packages and tools from host PC.

**Default username:password = ubuntu:ubuntu**

**Superuser username:password = root:root**

We recommended adapt ubuntu user as normal use, and adapt root user to do deveoping and debuging because Weston is running on root permission, it will not worked if you call GUI relate commands using "ubuntu user".

Features:
* LTS version until 2025/04
* Weston Desktop with GPU accelelation v1.18
* Wayland compositor v1.18.0
* gstreamer1.0 v1.16.2
* VPU libraries v1.18
* QT5 with GPU acceleration  v5.12.8 
* apt-get package manager
* openGL with GPU accelelation
* docker container v19.03.8

### Build-Image
-----------

#### Download the source code

Github way (Prepare git command first is recommended)

Install git first:

    $ sudo apt-get install repo

Download source code:

    $ git clone https://github.com/TechNexion-customization/ubuntu-tn-imx8.git

#### Compiling Environment Setup

General Packages Installation (Ubuntu 18.04 or above)

    $ sudo apt-get install gawk wget git git-core diffstat unzip texinfo gcc-multilib build-essential \
    chrpath socat cpio python python3 python3-pip python3-pexpect \
    xz-utils debianutils iputils-ping libsdl1.2-dev xterm \
    language-pack-en coreutils texi2html file docbook-utils \
    python-pysqlite2 help2man desktop-file-utils \
    libgl1-mesa-dev libglu1-mesa-dev mercurial autoconf automake \
    groff curl lzop asciidoc u-boot-tools libreoffice-writer \
    sshpass ssh-askpass zip xz-utils kpartx vim screen \
    debootstrap qemu-system-arm qemu-user-static gcc-aarch64-linux-gnu


