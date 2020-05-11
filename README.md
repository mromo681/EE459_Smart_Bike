# Smart Bike Accessary
## An embedded system created for EE 459 - Embedded Systems Design Laboratory.

The smart bike accessory is a multifunctional bike attachment designed to promote better health and safety for the rider. It has the ability to warn riders if there is a vehicle dangerously approaching from behind and can automatically toggle the bike light based on ambient light levels. It also provides the rider with important ride information such as the current time, location, speed, altitude, direction, and time travelled.

Report: [Insert Link Here]

The above report describes what modules were used and how to wire everything together.

This repository contains the source code that needs to be flashed on the microcontroller, and it also includes test files created to test the LCD and GPS modules.

## Main Program
The main program has source code in the lib/ and src/ folders.

To compile the program into a main.hex file you can use `make` or `make smart_bike` in the root directory.

To flash the program onto the microcontroller use `make flash` if the main.hex file was already created or `make smart_bike flash` if no main.hex file was made.

Flashing the microcontroller requires a 6-pin header to added as described [here](http://ece-classes.usc.edu/ee459/documents/AT328_Handout.pdf).

## Test Programs
The gps_functionality_check test can be run on a computer with gcc installed. This test simply demonstrates multiple GPS transmissions and prints the update of each string in the array after each sentence is parsed.

The test can be created by running `make gps_functionality_check` and then executing the `gps_func_check` executable created.


The other three tests need to be run on the microcontroller to test the LCD and GPS modules.

lcd_test will print messages on each row and then loop through every backlight color combination. This test can be flashed with `make lcd_test flash`

gps_read_test will print the messages transmitted by the GPS to the LCD in order to check for any errors. This test can be flashed with `make gps_read_test flash`

gps_update_test will only display the updated GPS information on the LCD in the same format as the smart_bike program and will rotate the displayed information accordingly. This test can be flashed with `make gps_update_test flash`
