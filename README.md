# ubuntu-server-auto-install

Creates an Ubuntu Server unattended installation ISO

Tested with Ubuntu Server 14.04, 16.04, 17.10, 18.04 and 18.10

## Prerequisites

* Need the isohdpfx.bin from isolinux. To get it, use `sudo apt install isolinux`
* Need 'xorriso' installed. To get it, use `sudo apt install xorriso -y`

## Features

* Minimal interaction
* Downloads available Ubuntu server release from releases.ubuntu.com
* Stores and used downloaded images in ~/Downloads
* By default uses the latest release
* Creates kickstart configuration for automatic (unattended) installation
* Alters grub configuration
* Creates default (sudoer) user as current user with password as username
* Copies ssh public key of current user
* Short - about 100 lines of code, easy modifiable
* Helps to run installation with qemu
* Suitable for batch installation
* Works with both UEFI & MBR Boot Options
  * _Works great with Hyper-V Gen1 and Gen2 VMs! (If using Gen2, set Secure Boot Template to "Microsoft UEFI Certificate Authority"_

## Interface

* No arguments - interactive mode. The program requestes desired version XX.YY.
* Argument - XX.YY of Ubuntu server version. The program finds the third release digit automatically.
  For example "16.04.4".
* Argument - word "latest" - the latest release will be selected automatically, for example 17.04.
* Argument - URL of iso image to download (if need).
* Argument - name for iso image. Program will search for the file in directory ~/Downloads
* Output - file ubuntu-XX.YY.ZZ-server-amd64-auto-install.iso

## Limitations

* Doesn't work with Ubuntu desktop ISOs
* May or may not work with other versions of Ubuntu Server
  * _Does not work with Ubuntu Server 12.04_