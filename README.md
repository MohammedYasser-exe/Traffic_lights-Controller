# Traffic_lights-Controller
The goal of this project is to design a traffic light control system.
The system contains simply two traffic lights.
One allows cars to move from north to south, and the other one allows cars to move from east to west.
Beside each traffic there is also a pedestrian traffic light. The pedestrian has to press on a button to have his light green to cross the street safely

1. Set the normal traffic Light
Use one of the timers to have the two car traffic lights working. The traffic light shall stay
GREEN for 5 seconds, then YELLOW for 2 seconds, then turns RED. When one of the
traffic lights is set to RED the other one has to go GREEN exactly after 1 second. The
same sequence then is repeated again.
GREEN : 5 seconds
YELLOW: 2 seconds
Then RED.
Wait 1 second, then start the sequence on the other traffic.

2. Implement the pedestrian Traffic Light
Use two push buttons and 4 LEDs for this system. There will be two pedestrian traffics,
each with a push button and 2 LEDS: GREEN and RED. Whenever a pedestrian presses
the button, the traffic light that is green shall be interrupted, and the pedestrian traffic
light will be green for 2 seconds. Then it will be back to RED and the traffic light that was
interrupted will resume from when it was paused.
Example: If the car traffic light was green for 2 seconds and interrupted it will then
resume the remaining 3 seconds to finish the 5 seconds.

3.1 Handling first case:
When two pedestrians pushed the button together in two different traffics
• Both pedestrian lights turn into green and both traffic lights turn into red for two seconds.
• After 2 seconds both pedestrian lights turn into red and the traffic lights return to their previous states.
Use two timers each one for each pedestrian to maintain this part

3.2 Handling Second case:
When the same button was being pressed more than one time during the same period of pedestrian crossing.
• The pedestrian lights ignore any new button pressings and continue its 2 second time.
Implementation:
Use if condition to check green value for register of pedestrian and return if true

3.3 Handling Third case:
Delaying the request of the pedestrian to cross if the button was pressed after 1 second from the end of the Period of pedestrian crossing.
• The pedestrian lights delay any new button pressings until 1 second has passed from the last
Use flag disable it in the end of Timer ISR and enable it after one second in Timer0 interrupt
