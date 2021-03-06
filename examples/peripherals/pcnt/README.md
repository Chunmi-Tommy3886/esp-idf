# Example: pcnt

This example uses the pulse counter module (PCNT) to count the rising edges of the PWM pulses generated by the LED Controller module (LEDC).

The examples is setting up and then using the following GPIO pins:
  * GPIO18 - output pin of a sample 1 Hz pulse generator,
  * GPIO4 - pulse input pin,
  * GPIO5 - control input pin.

The configuration parameters of this example (pin numbers, etc.) may be modified at the top of the `main/pcnt_test.c` file.

## Run the Test

1, Compile and load the example.
2. Open a serial port monitor to view the message printed out on your screen.
3. Connect GPIO18 with GPIO4.
4. GPIO5 is the control signal, you can leave it floating with internal pull up, or connect it to ground. If left floating, the count value will be increasing. If you connect GPIO5 to GND, the count will be decreasing.


## Check Functionality

The example will print out the current counter values and events. 

An interrupt will be triggered when the counter value:
  * reaches 'thresh1' or 'thresh0' value,
  * reaches 'l_lim' value or 'h_lim' value,
  * will be reset to zero.

A sample output on the serial monitor:

```
Current counter value :-1
Current counter value :-2
Current counter value :-3
Current counter value :-4
Event PCNT unit[0]; cnt: -5
THRES0 EVT
Current counter value :-5
Current counter value :-6
Current counter value :-7
Current counter value :-8
Current counter value :-9
Event PCNT unit[0]; cnt: 0
L_LIM EVT
ZERO EVT
Current counter value :0
Current counter value :-1
...
```
  
See the README.md file in the upper level 'examples' directory for more information about examples.
