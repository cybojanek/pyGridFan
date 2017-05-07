# pyGridFan

Python command line controller for NZXT GRID+ V2

Tested on Linux

Requires python3 and pyserial package

Usage:

```bash
gridfan DEVICE_PATH help
gridfan DEVICE_PATH get all|1|2|3|4|5|6
gridfan DEVICE_PATH set 1|2|3|4|5|6 0|20|21|...|100
```

Where DEVICE_PATH is something like "/dev/ttyACM0".

# Notes

* The get result is RPM, while set is a percentage (0 - off, 100 - full).

* When setting the speed from 0 to anything else, the controller temporarily sets the speed to 100, then throttles to the desired setting (most likely to provide enough power to jump start the fan)

* Setting the speed too low (varies with fan), can result in an oscillating speed (not enough power, the fan turns off, and the controller tries to compensate).
