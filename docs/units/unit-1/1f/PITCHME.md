---
# Robotics

UCMHS Robotics / Fall 2018 / Ms. Gerstein
---
## Today's Goals

* Use code to control a circuit
* Control inputs and outputs
---
## Do Now

* Open up sub assignment for me to check
* Complete do now on Google Classroom
---
## Arduino

* 5V, mostly digital logic
* All outputs digital
* Can simulate analog
* Has analog inputs
---
## Code Structure

```arduino
void setup(){
    // Whatever goes in here runs once when Arduino starts
}

void loop(){
    // Whatever goes in here will run repeatedly
}
```
---
# Blink

Simplest example that actually does something
---
```arduino
int ledPin = 13;

void setup()
{
  pinMode(ledPin, OUTPUT);
}

void loop()
{
  // turn the LED on (HIGH is the voltage level)
  digitalWrite(ledPin, HIGH);
  delay(1000); // Wait for 1000 millisecond(s)
  // turn the LED off by making the voltage LOW
  digitalWrite(ledPin, LOW);
  delay(1000); // Wait for 1000 millisecond(s)
}
```
@[1](Declare and initialize a variable)
@[3-6](Setup)
@[5](Set pin mode)
@[8-16](Loop)
@[11,14](Digital write)
@[12,15](Delay)
@[10,13](Comment)
---
## Try It

Use what you see here to blink two LEDs in opposition to each other
---
# Analog(ish)
---
## PWM and Analog Write

* Turns pin on/off *very* fast
* Actual voltage is still 5v - current limiting still needed
* Only available on marked pins
---
## Analog Write
```arduino
const int ledPin = 3;

void setup()
{
  pinMode(ledPin, OUTPUT);
}

void loop()
{
  // Set the LED to full brightness
  analogWrite(ledPin, 255);
  delay(1000);
  // Turn the LED off
  analogWrite(ledPin, 0);
  delay(500);
  //Set the LED to ~1/3 brightness
  analogWrite(ledPin, 85);
  delay(500);
}
```
@[1](Made the variable a constant so it won't change)
@[11,14,17](analogWrite())
---
## Try It

Use an Arduino to control the anodes of an RGB LED and program a pattern of colors in (for example, a rainbow)