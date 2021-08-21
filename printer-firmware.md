## Basic processing

The arduino will read serial communications from the computer, where int representing the time (in ms) of powering for each motors to reach the correct coordinates on the tray will be sent. If the value received is negative, the motor polarity will be inverted and the absolute value will be taken.