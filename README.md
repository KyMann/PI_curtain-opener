# PI_curtain-opener
calculates dawn and dusk and operates a motor based on those times.

--Credits--
Based heavily on a modified sunrise.py module written by Michael Anders in 2010 as an alternative to PyEphem. 
Also uses the general motor control format from Matt, the Raspberry Pi Guy. 

--How it works--
based on an RTK motor control board. (Touches pins, 17,18 and 22,23 for two motors)



After understanding the sunrise module, the necessary GPIO bits, there is the call to sunrise using the current Date.
Then there is a single function defined to control the motor. three arguments, forwards_pin, backwards_pin, and revtime
And then a series of if statements that call that function. The pins will need to be switched in the second if statement.
Also the time will have to be found for a specific curtain setup from trial and error, using your motor.
The if statements are nestled in a while statemtnt to allow keyboard interrupts. 

--
The code should be linked to your chrontab. This is superior to adding simple open times to the chrontab because it adjusts dynamically
toboth the seasons and the solar analemma (apparent sun movement caused by the earth's axis wobble). 
