# Arduino-Smoke-Detection-System
IoT Fire Safety: Intelligent Gas & Smoke Detection
----------------
This project goes over 2 objectives:
1) Creating an alarm that alerts in the case of a fire, smoke and gas leaks
2) Integrating the use of a Ubuntu-based server for data logging and displaying data on an iot dashboard.
-----------------
Key Features:
1) Uses rolling average to avoid false readings.
2) extremely simple to set up.
-----------------
Future developments:
1) Adding wifi connectivity
2) Allow data to be sent to a home server/ public server
3) Add other air quality sensors
4) Create a dashboard to display readings
-----------------
Hardware:
1) Microcontroller: Arduino
2) Sensors: MQ-2 gas & smoke sensor (Any other suitable sensor could also be used)
3) Actuators: Buzzer (MB12A12)
4) Breadboard
5) jumper wires
-----------------
Software:
1) Arduino IDE
-----------------
Arduino Code:
```cpp
const int smokeRead = A0;
const int buzzer = 2;

void setup() {
 Serial.begin(9600);
 pinMode(buzzer, OUTPUT);
}
void loop() {
  //printing ouputs for debugging and calibration
  float aveSmoke = 0;
  int sample = 5;
  int total =0;
  int sensorVal = 0;
  for(int i = 0; i< sample;i++  ){
      sensorVal = analogRead(smokeRead);
      total = total + sensorVal;
  }
    aveSmoke = total/sample;
    Serial.println(sensorVal);
    Serial.println(aveSmoke);
  //THRESHOLD SHOULD BE SET HERE WHEN CALIBRATING IN PLACE OF 670
  if(aveSmoke > 670 ){
    digitalWrite(buzzer, HIGH);
  }
  else{
    digitalWrite(buzzer, LOW);
  }
  delay(500);
}
```
------------
Circuit connection:



