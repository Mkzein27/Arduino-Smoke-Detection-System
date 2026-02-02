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
 
 //indicator of power on
  digitalWrite(buzzer, HIGH);
  delay(100);
  digitalWrite(buzzer,LOW);
  //Sart up phase for sensor to heat and give stable readings (5 minutes)  delay(100);
  for(int t = 0; t < 300 ; t++){
    delay(1000);
  }
  //chirp indicating end of warm up
  digitalWrite(buzzer, HIGH);
  delay(100);
  digitalWrite(buzzer, LOW);
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
    aveSmoke = (float)total/sample;
    Serial.println(aveSmoke);
  //buzzer condition
  if(aveSmoke > 500 ){
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
1) Connect MQ-2 AO pin into A0 pin on arduino
2) Connect MQ-2 GND pin to GND on arduino or breadboard
3) Connect MQ-2 VCC to 5V pin on arduino
4) Connect positive pin of buzzer(marked with +) to digital output pin 2 on arduino
5) Conncet other pin on buzzer to GND



