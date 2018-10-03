---
# Robotics

UCMHS Robotics / Fall 2018 / Ms. Gerstein
---
## Today's Goals

* Use code to control a circuit
* Control inputs and outputs
---
## Do Now

* Finish and submit last class's pushbutton circuit
* Can you set up your circuit so when the LED turns on or off, it stays that way until the next time it's pressed?
---
## Tracking states

* Pushbutton is momentary
* Sometimes changes should last until next press, not until it's released
* This is applicable to any sort of input, not just pushbutton
---
## Circuit

* Circuit can be same as previous assignment - make a copy of it if you wish
* My example will have input on pin 2 and LED on pin 3
---
## ledState

```arduino
int buttonPin = 2;
int buttonState = 0;;
int oldButton = 0;
int ledPin = 3;
int ledState = 0;

void setup(){
    Serial.begin(9600);
    pinMode(buttonPin, INPUT);
    pinMode(ledPin, OUTPUT);
}

void loop(){
    buttonState = digitalRead(buttonPin);
    if (buttonState != oldButton) {
        if (ledState == 0) {
            ledState = 1;
        }
        else {
            ledState = 0;
        }
    }
    Serial.println(buttonState);
    oldButton = buttonState;
    digitalWrite(ledPin, ledState);
    delay(50);
}
```
---
## Try It

Combine this with `analogWrite()` to cycle through a sequence of colors each time you press the button.

Also, consider how tracking states could be useful for a robot.