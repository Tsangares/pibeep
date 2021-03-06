## Context

This tool is showcased in the project [IotaWorkshop](https://github.com/Tsangares/iotaworkshop)

# Summary

This is a beeping utility for the common buzzer. This package comes with a variety of beeps that can be called from a command line inteface or imported from python.

# Installation

This package requires `RPi.GPIO`, which I installed on arch arm using

    yay -S python-raspberry-gpio
	
But ubuntu or rasbian can use,

    pip install RPi.GPIO

To install pibeep simply install the pip package.

    pip install pibeep
	
You can then look at the examples on how to run as a cli. You can also import it into your project using,

	from pibeep import pulseBeep,beepDuration
	beepDuration(pin=12,duration=.33) #beeper on pin 12, on for .33 sec
	pulseBeep(pin=12,freq=25,duration=1) #pulse beep at 25HZ for 1 seccond


# Beeps

 - short: duration 0.05 sec
 - medium: duration 0.25 sec
 - long: duration 1.00 sec
 - warning: pulses 8HZ for 1.5 sec duration
 - confirmed: pulses 16HZ for .5 sec duration
 - brr: pulses 50HZ for .5 sec duration
 
# Example

The cli can be use any of the listed above beeps in the format as the following commands:

    beep warning --pin 12 #Warning sound
    beep short --pin 12 #Small beep
	beep brr --pin 12 #A rumbling sound
	beep confirmed --pin 12 #A sound that conveys success

Usually I need to run it as sudo to have the correct permissions, but it depends on your setup. 
