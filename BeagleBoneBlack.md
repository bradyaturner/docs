Getting Started
======

Loading Firmware
-----

* Image downloads: http://beagleboard.org/latest-images

1) Identify SD Card:
```bash
df -h

Filesystem                          Size   Used  Avail Capacity  iused    ifree %iused  Mounted on
/dev/disk1s1                        70Mi  1.5Mi   69Mi     3%      512        0  100%   /Volumes/BEAGLE_BONE
```

* "Filesystem" is the identifier used in the next steps

2) Write image to SD card:
```bash
Unmount disk
# sudo diskutil unmount $FILESYSTEM
sudo diskutil unmount /dev/disk1s1

# sudo dd bs=1 if=$PATH_TO_IMG of=$FILESYSTEM
sudo dd bs=1 if=bone-debian-8.2-tester-2gb-armhf-2015-11-12-2gb.img of=/dev/disk1s1

# monitor dd progress
sudo kill -INFO $(pgrep ^dd$) # OS X
sudo kill -USR1 $(pgrep ^dd$) # LINUX
```


Links
----
* http://beagleboard.org/latest-images
* https://learn.adafruit.com/beaglebone-black-installing-operating-systems/mac-os-x
* https://learn.adafruit.com/beaglebone-black-installing-operating-systems/flashing-the-beaglebone-black
