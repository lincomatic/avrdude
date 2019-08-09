
# AVRDUDE for multiple USBasps

## Description
- based on avrdude 6.3 sources

- added support for multiple USBasp programmers.

## Usage 

### form 1

-P busnum:devicenum - use the USBasp with bus number *busnum* and device number *devicenum*
```
$ avrdude -cusbasp -pm328p -P3:1
```
Tip: to find a bus/device numbers of a particular USBasp, remove all other USBasps, and plug just one USBasp into the target USB port. Then run avrdude without the -P parameter:
```
$ avrdude -c usbasp -p m328p
avrdude: *** SCL version ***
avrdude: Found USBasp, bus:device: 3:3
```

### form 2

-P idx:n - use the nth USBasp encountered during bus enumeration, starting with 0

e.g. in a system with 2 USBasp's plugged in

select first USBasp
```
$ avrdude -c usbasp -p m328p -P idx:0
```
select second USBasp
```
$ avrdude -c usbasp -p m328p -P idx:0
```

## BUILDING
```
sudo apt-get install libusb-1.0-0-dev flex bison
./configure
make
make install
```