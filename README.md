## servo motor
- Servo has three wires: brown is ground , red is power and orange is signal.
- so connect the servo to the breadboard using pins, the brown would go to the ground bus, the red wire would go to the power bus, and the orange would go to one of the arduino's digital pins.

-when using this many motors at once it's important to think about power. in a single Servo motor you can just power that motor directly from the arduino's 5 volt pin, how ever, that pin can only provide up to 1 amp and you may exceed that when when using this many motors at once, so even though the UNO provides the correct voltage it does not provide enough current and (you can't use it to directly power this many motors). instead you can use external Polymer battery and an external voltage regulator that has a higher current rating.

-to control the servos you need to :
1- include the Servo library ```(#include <Servo.h>)```
2- create a servo object for each motor, it might help to give them names that makes sense to you.
3-define srarting angle: It helps to use variable to define the various angles that you want to move the legs to.
4- Attach Servo motors to pins: in your setup function you need to attach each Servo object to an arduino pin, make sure you keep track of wich motor is attached to which pin.
5-Set start angle for each motor: Use the (write) command to set the starting position for each motor, example:
```
leg1.write(start_angle);
```

6-specify a long delay which gives you time to put the robot down and make sure it's standing up  ```delay(5000)```

7- Enter the loop function where you can program your gate using right commands to change the angle of each motor

8- Use a while loop where you icrementally change the angle just one or two degrees at a time and that is going to result is smoother motion.
