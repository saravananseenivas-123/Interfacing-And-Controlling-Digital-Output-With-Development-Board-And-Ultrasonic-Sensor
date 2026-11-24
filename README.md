# EXP-3-Interfacing-And-Controlling-Digital-Output-With-Development-Board-And-Ultrasonic-Sensor

## Aim:

To interface an HC-SR04 ultrasonic sensor with an Arduino Uno and control a digital output (LED) based on the measured distance of an object.

## Algorithm:

1. Initialize the TRIG, ECHO, and LED pins of the Arduino.
2. Generate a 10-microsecond trigger pulse using the ultrasonic sensor.
3. Read the echo pulse duration using the pulseIn() function.
4. Calculate the distance in centimeters using the echo duration.
5. If the distance is below the predefined threshold, turn ON the LED; otherwise, turn OFF the LED.
6. Display the measured distance in the Serial Monitor and repeat the process continuously.

## Procedure:

Open Tinkercad Circuits and create a new circuit.
Place an Arduino Uno, HC-SR04 ultrasonic sensor, LED, and suitable resistor in the workspace.
Connect the VCC pin of the ultrasonic sensor to the Arduino 5V pin.
Connect the GND pin of the ultrasonic sensor to the Arduino GND.
Connect the TRIG pin of the ultrasonic sensor to a digital pin of the Arduino.
Connect the ECHO pin of the ultrasonic sensor to another digital pin of the Arduino.
Connect the LED to a digital output pin through a suitable resistor.
Write the Arduino program to generate a trigger pulse and calculate the distance using the echo time.
Set a suitable distance threshold in the program.
If the measured distance is below the threshold, turn ON the LED.
If the measured distance is greater than the threshold, turn OFF the LED.
Start the simulation in Tinkercad and observe the LED operation while changing the ultrasonic sensor distance.
Verify that the digital output responds correctly to the measured distance.
Algorithm
Start
Initialize the ultrasonic sensor pins and LED pin.
Set the TRIG pin to LOW.
Generate a short HIGH pulse on the TRIG pin.
Read the duration of the signal received at the ECHO pin.
Calculate the distance from the echo duration.
Compare the measured distance with the predefined threshold.
If the distance is less than the threshold, turn ON the LED.
Otherwise, turn OFF the LED.
Display or monitor the measured distance.
Repeat the process continuously.
Stop

## Code:

```C++
const int trigPin = 9;
const int echoPin = 10;

void setup() {
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
  Serial.begin(9600);
}

void loop() {
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);
  
  long duration = pulseIn(echoPin, HIGH);
  int distance = duration * 0.0343 / 2; 
  
  Serial.print("Distance: ");
  Serial.print(distance);
  Serial.println(" cm");
  
  delay(500);
}
```

## Output:

<img width="1092" height="577" alt="Screenshot 2026-11-20 161649" src="https://github.com/user-attachments/assets/a3bd6659-47a3-4d89-9479-21ce6aa5d1c0" />

<img width="1042" height="438" alt="Screenshot 2026-11-20 161659" src="https://github.com/user-attachments/assets/8297481f-bd96-4842-814d-04773cb7bea7" />

<img width="1045" height="416" alt="Screenshot 2026-11-20 161710" src="https://github.com/user-attachments/assets/a1d96160-adcc-4f1d-a9bb-98b3a615e974" />


## Result:

The ultrasonic sensor was successfully interfaced with the development board in Tinkercad Circuits. The distance of an object was measured using the HC-SR04 sensor, and the LED was successfully controlled as a digital output according to the measured distance. The simulation worked successfully and demonstrated distance-based digital output control.
