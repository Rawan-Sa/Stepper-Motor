# Stepper-motor
# Tinkercad was used to write the code and design the Stepper motor circuit.
# arduino Uno R3 and DC motor with encoder was the main parts to make the Stepper motor circuit.

#include <Stepper.h>:

const int stepsPerRevolution = 120;

Stepper myStepper (stepsPerRevolution , 1 , 9 , 10 , 11);

int stepCount = 0;

void setup() {
Serial.begin(9600);

}

void loop() {
  int sensorReading = analogRead(A0);
  int motorSpeed = map(sensorReading , 0 , 1023 , 0 , 250); 
  if (motorSpeed > 0 ){
   myStepper.setSpeed(motorSpeed);
    myStepper.step(stepsPerRevolution / 100);
    
  }
}
