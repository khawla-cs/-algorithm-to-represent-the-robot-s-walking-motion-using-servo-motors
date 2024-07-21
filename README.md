## servo motor

![تنزيل](https://github.com/user-attachments/assets/844f3550-1d76-4f24-9fdf-3f60bcf308c4)


- Servo has three wires: brown is ground , red is power and orange is signal.
- so connect the servo to the breadboard using pins, the brown would go to the ground bus, the red wire would go to the power bus, and the orange would go to one of the arduino's digital pins.

- when using this many motors at once it's important to think about power. in a single Servo motor you can just power that motor directly from the arduino's 5 volt pin, how ever, that pin can only provide up to 1 amp and you may exceed that when when using this many motors at once, so even though the UNO provides the correct voltage it does not provide enough current and (you can't use it to directly power this many motors). instead you can use external Polymer battery and an external voltage regulator that has a higher current rating.

## Algorithm to represent the robot's walking motion (in four legs) using servo motors :
### 1- include the Servo library
```(#include <Servo.h>)```

### 2- create a servo object for each motor
it might help to give them names that makes sense to you.
```
Servo leg1;
Servo leg2;
Servo leg3;
Servo leg4;


Servo knee1;
Servo knee2;
Servo knee3;
Servo knee4;
```

### 3-define srarting angle
It helps to use variable to define the various angles that you want to move the legs to.
```
//int start_angle = 90;

int knee_delta = 60;
int leg_delta = 45;
```
### 4- Time between motins(millisecond)
```
int delayTime = 500;
```

### 5- Attach Servo motors to pins
in your setup function you need to attach each Servo object to an arduino pin, make sure you keep track of wich motor is attached to which pin.
```
leg1.attach(2);
leg2.attach(4);
leg3.attach(8);
leg4.attach(10);

knee1.attach(3);
knee2.attach(5);
knee3.attach(9);
knee4.attach(11);
```

### 6-Set start angle for each motor
Use the (write) command to set the starting position for each motor, example:
```
leg1.write(start_angle);
leg2.write(start_angle-leg_delta);
leg3.write(start_angle+leg_delta);
leg4.write(start_angle);

knee1.write(start_angle);
knee2.write(start_angle);
knee3.write(start_angle);
knee4.write(start_angle);
```

### 7-specify a long delay
which gives you time to put the robot down and make sure it's standing up 
```delay(5000)```


### 8- Enter the loop function
where you can program your gate using right commands to change the angle of each motor.

### 9- Use a while loop
where you icrementally change the angle just one or two degrees at a time and that is going to result is smoother motion.

reference: www.sciencebuddies.org
