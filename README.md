# Arduino-Smoke-Detection-System
IoT Fire Safety: Intelligent Gas & Smoke Detection
Developed by Mohamed Khaled Zein A Mechatronics Engineering Project integrating Embedded Systems and Linux Infrastructure.
-----------------
This project goes over 2 objectives:
1) Creating an alarm that goes of in the case of a fire, smoke and gas leaks
2) Integrating the use of a Ubuntu-based server for data logging and displaying data on an iot dashboard.
-----------------
Key Features:
1) Fail safe design: even if network connection is lost, buzzer still alerts.
2) Implements rolling average filter to avoid false positives.
3) Linux server integration: Data is transfered to a Ubuntu server for long term analysis
-----------------
Future developments:
1) In the future the goal would be to create an open source home monitoring application to send notifications, in case the house is empty.
2) Air quality readings.
-----------------
Hardware:
1) Microcontroller: Arduino / ESP board
2) Sensors: MQ-2 gas & smoke sensor (Any other suitable sensor could also be used)
3) Actuators: Buzzer (MB12A12)
4) Breadboard
5) jumper wires
6) Server(optional for data logging): Computer running Ubuntu-Server or any configured server with NAS set up (You could also refer to my server set up guide :))
-----------------
Software:
1) Arduino IDE
2) Samba (server) for data logging
-----------------
Step 1: Connecting the circuit, refer to ()
Step 2: Connect the Arduino to a computer that has Arduino IDE running.
Step 3: copy the code in the () and paste it into the IDE.


