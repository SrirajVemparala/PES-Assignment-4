# PES-Assignment-4

Project name: Buffahiti Traffic Lights

State Machine Logic:
A finite state machine is used to implement the application and four states are used :

STOP
GO
WARNING
CROSSWALK

Here traffic lights states are solid states for STOP,GO,WARNING and no blinking is observed during this transition and if no touch slider is observed the flow of transition will be like this :STOP -> TRANSITION -> GO -> TRANSITION ->WARNING->TRANSITION->STOP and it continues.

When touch is detected flow will be like this
CURRENT ->CROSSWALK_TRANSITION->CROSSWALK->GO->TRANSITION->WARNING->TRANSITION->STOP and so on.

The traffic light should transition from one state to other in a period of 1sec, no more or no less.
In debug mode, each of the STOP and GO states should hold the color for 5 sec and WARNING state should hold the color for 3 seconds with a transition period of 1 sec between all states.
In production mode, the STOP and GO states hold the LED color for 20 seconds each and WARNING state for 5 seconds.
In the CROSSWALK state the light blinks 250 msec off, 750 msec on. In all other states, the light is solid (not blinking).

Approach:
A Systick timer module is configured at 10 msec to maintain the time between each transition.
A delay was maintained for crosswalk so that it might not interfere with other counters.
A PWM module is configured to maintain and control the LED colors and the transitions
