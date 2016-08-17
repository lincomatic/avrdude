based on avrdude 6.3 sources

added support for multiple USBasp programmers.

-P idx:n - use the nth USBasp encountered on the bus, starting with 0

e.g. in a system with 2 USBasp's plugged in

select first USBasp
avrdude -c usbasp -p m328p -P idx:0
select second USBasp
avrdude -c usbasp -p m328p -P idx:0