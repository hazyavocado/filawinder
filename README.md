# filawinder

based on the code by Ian Johnson
https://www.thingiverse.com/thing:174383


All my problems started when I bought a Filabot. The winder was too slow so I added gears to make it spin faster:
https://www.thingiverse.com/thing:2912099

Then the filament went up and down a lot as the motor cycled on and off too much. It was speeding up/down too rapidly. Also it was going too fast. So here we are. The changes are all made to FilaWinder_11.ino:

Below changes max motor speed. Default is 1.7, i'm running it at 0.4:
290  int ScaledOutput = (Output * 0.4);             //Scale the Output from 0-150 to 0-255)   default is output * 1.7  



Below is accel. It speeds up at 20 units/cycle:
295 if ( (puller_speed - puller_speed_old) > 20) puller_speed = puller_speed_old + 20; //default is 25



Decel is -4 u/c:
296  if ( (puller_speed - puller_speed_old) < -4) puller_speed =  puller_speed_old - 4;  //default is 25



Anyway, i just plugged the arduino into my laptop while it was spooling and reflashed it to test various configurations. I'd recommend dialing in the values that way if you need to adjust it.
