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
int buttonState = 0;
int ledPin = 3;
int ledState = 0;
// How can we keep track of the current state of the LED?

void setup(){
  Serial.begin(9600);
  pinMode(2, INPUT);
  pinMode(3, OUTPUT);
}

void loop(){
  // How can we tell if the current state of
  // the button is different from previous?
  if (digitalRead(buttonPin) == 1 && digitalRead(buttonPin) != buttonState) {
    // will run if button state has changed
    Serial.println("It's changed");
    if (ledState == 0) {
      ledState = 1;
    }
    else {
      ledState = 0;
    }
    
  }
  buttonState = digitalRead(buttonPin);
  // if ledState is high, turn LED on
  if (ledState == 1){
    digitalWrite(ledPin, HIGH);
  }
  // otherwise turn it off
  else {
    digitalWrite(ledPin, LOW);
  }
  Serial.println(buttonState);
  delay(50);
}
```
---
Updated version of changing states

```arduino
int buttonState;
int oldButtonState;
int ledState = 0;

const int buttonPin = 2;
const int ledPin = 3;

void setup(){
    pinMode(buttonPin, INPUT);
    pinMode(ledPin, OUTPUT);
    Serial.begin(9600);
    Serial.print("Ready!");
    buttonState = digitalRead(buttonPin);
    oldButtonState = digitalRead(buttonPin);
}

void loop(){
    buttonState = digitalRead(buttonPin);
    if (buttonState != oldButtonState && buttonState == 1) {
        Serial.println("You pushed the button");
        // ledState = !ledState; // toggle between two states
        if (ledState == 0) {
            ledState = 1;
        }
        else {
            ledState = 0;
        }
    }

    digitalWrite(ledPin, ledState);

    oldButtonState = buttonState;
    delay(50);
}
```
---
## Try It

Combine this with `analogWrite()` to cycle through a sequence of colors each time you press the button.

Also, consider how tracking states could be useful for a robot.
