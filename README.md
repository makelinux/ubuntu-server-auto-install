# ubuntu-server-auto-install

Creates any Ubuntu server unattended installation iso

Tested in Ubuntu server versions 12.04 14.04 15.04 16.04 16.10 17.04

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

Interface:

* No arguments - interactive mode. The program requestes desired version XX.YY.
* Argument - XX.YY of Ubuntu server version. The program finds the third release digit automatically.
  For example "14.04.5".
* Argument - word "latest" - the latest release will be selected automatically, for example 17.04.
* Argument - URL of iso image to download (if need).
* Argument - name for iso image. Program will search for the file in directory ~/Downloads
* Output - file ubuntu-XX.YY.ZZ-server-amd64-auto-install.iso

Limitations:

* Doesn't work with Ubuntu desktop
