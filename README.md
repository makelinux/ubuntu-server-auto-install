# ubuntu-server-auto-install

**_PLEASE NOTE: I did not create the base version of this script, nor do I take credit. I made a less functional version building off of the wonderful work by [makelinux](https://github.com/makelinux/ubuntu-server-auto-install) to fit my needs._**

Creates an Ubuntu Server 16.04 unattended installation ISO

_This was originally designed to work with more than just 16.04, but I have no need for backwards compatibility. I am leaving the functionality to download older server versions, however I cannot say they will work, and in fact I presume they do not work._

Features:

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
* UEFI & MBR Boot Options
  * _Works great with Hyper-V Gen1 and Gen2 VMs!_

Interface:

* No arguments - interactive mode. The program requestes desired version XX.YY.
* Argument - XX.YY of Ubuntu server version. The program finds the third release digit automatically.
  For example "16.04.4".
* Argument - word "latest" - the latest release will be selected automatically, for example 17.04.
* Argument - URL of iso image to download (if need).
* Argument - name for iso image. Program will search for the file in directory ~/Downloads
* Output - file ubuntu-XX.YY.ZZ-server-amd64-auto-install.iso

Prerequisites:

* Need the isohdpfx.bin from isolinux. To get it, use `sudo apt install isolinux`
* Need 'xorriso' installed. To get it, use `sudo apt install xorriso -y`

Limitations:

* Doesn't work with Ubuntu desktop
* May or may not work with other versions of Ubuntu Server
