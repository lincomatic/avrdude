
# AVRDUDE for multiple USBasps

## Description
- based on avrdude 6.3 sources

- added support for multiple USBasp programmers.

## Usage

-PS - scan for all USBasps

after scanning, specify port of target USBasp as displayed in the scan

e.g.

avrdude -c usbasp -pm328p -PS
avrdude: *** SCL version ***
Scanning for USBasps...
avrdude: Found USBasp: 1:5.1:1.1:0
avrdude: Found USBasp: 1:3.1:2.1:1.1:0

avrdude -c usbasp -pm328p -P1:3.1:2.1:1.1:0


## BUILDING
```
sudo apt-get install libusb-1.0-0-dev flex bison
$ ./configure
$ make
$ make install
```

If make fails with
```
/bin/bash: aclocal-1.15: command not found
Makefile:706: recipe for target 'aclocal.m4' failed
make: *** [aclocal.m4] Error 127
```
do
```
$ apt install autoconf libtool
$ autoreconf -f -i
```
then try again from the ./configure step
 
