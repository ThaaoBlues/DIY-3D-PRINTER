## Basic processing
The app basically process G-code and send motor's running time to the arduino.

## Data needed before processing
* $H$ the printer's head height (int)
* $L$ the lenght travelled on this axis in one axis motor's revolution (int)
* $T$ the time in milliseconds the motor takes for one revolution (rotation speed in ms) (int)
* $v$ the lenght in centimeters travelled by a cart on an axis in one millisecond calculated with the two int upper as :
	> $v = \frac{L}{R}$
* $Z$ the printing tray's length
* $X$ the printing tray's width
* $P$ the plastic cable thickness 
## Data processing
1. Get the last head position (if it's start, get to $x = \frac{X}{2}; z = \frac{Z}{2}; Y = H+P$ )
2. calculate $\Delta$ the difference between the last and future position (tuple).
3. calculate $t$ the time of powering for each axis's motor with ($tz$ is 0 if no slice change):
	> $tx = v*\Deltax; ty=v*\Deltay; tz = v*\Deltaz$
