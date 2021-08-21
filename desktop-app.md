## Basic processing
The app basically process G-code and send motor's running time to the arduino.

## Data needed before processing
* <img src="https://render.githubusercontent.com/render/math?math=H"> the printer's head height (int)
* <img src="https://render.githubusercontent.com/render/math?math=L"> the lenght travelled on this axis in one axis motor's revolution (int)
* <img src="https://render.githubusercontent.com/render/math?math=T"> the time in milliseconds the motor takes for one revolution (rotation speed in ms) (int)
* <img src="https://render.githubusercontent.com/render/math?math=v"> the lenght in centimeters travelled by a cart on an axis in one millisecond calculated with the two int upper as :
	<img src="https://render.githubusercontent.com/render/math?math=v = \frac{L}{R}">
* <img src="https://render.githubusercontent.com/render/math?math=Z"> the printing tray's length
* <img src="https://render.githubusercontent.com/render/math?math=X"> the printing tray's width
* <img src="https://render.githubusercontent.com/render/math?math=P"> the plastic cable thickness 
## Data processing
1. Get the last head position (if it's start, get to <img src="https://render.githubusercontent.com/render/math?math=x = \frac{X}{2}; z = \frac{Z}{2}; Y = H+P )">
	
2. calculate <img src="https://render.githubusercontent.com/render/math?math=\Delta"> the difference between the last and future position (tuple).
3. calculate <img src="https://render.githubusercontent.com/render/math?math=t">the time of powering for each axis's motor with (<img src="https://render.githubusercontent.com/render/math?math=tz"> is 0 if no slice change):
	<br>
	<img src="https://render.githubusercontent.com/render/math?math=tx = v*\Delta{x}">
	<br>
	<img src="https://render.githubusercontent.com/render/math?math=ty=v*\Delta{y}">
	<br>
	<img src="https://render.githubusercontent.com/render/math?math=tz = v*\Delta{z}">
	
4. send the results to the arduino
