---
# Robotics

UCMHS Robotics / Fall 2018 / Ms. Gerstein
---
## Today's Goals

* Use code to control a circuit
* Control inputs and outputs
---
## Do Now

* Open up work from last class for me to check
* Submit a share link to your assignment from last class in Google Classroom
---
## Review

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
@[1]
@[3-6]
@[5]
@[8-16]
@[11,14]
@[12,15]
@[10,13]
---
## More Review

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
@[1]
@[11,14,17]
---
## Repetition

How would you fade an LED from 0 brightness to 255 brightness and back again?
---
## While loops

```arduino
int i = 0;

while (i < 255){
  analogWrite(9, i);
  i++;
}
```
@[1](Setting up a variable to use for counting)
@[3-5](while loop)
---
## For loops

```arduino
for( int i = 0; i < 255; i++){
  analogWrite(9, i);
}
```
---
## Try it

* Fade an LED on and off. Can you set the speed to be faster in one direction than the other?
* Fade an RGB LED through the rainbow
* Submit both in Google Classroom
