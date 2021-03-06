---
# Robotics

UCMHS Robotics / Fall 2018 / Ms. Gerstein
---
## Today's Goals

* Use code to control a circuit
* Control inputs and outputs
---
## Do Now

* Finish rainbow LED
---
## Inputs

* Analog or digital
* Read instead of write
* Send information to Arduino
---
## Pushbutton Wiring

* Connect 1 pin of button to 5V
* On pin not connected to that one, connect to GND through 10k resistor
* Connect other side of push button to a digital I/O pin
---
# Serial

Display information in serial monitor
---
```arduino
void setup()
{
  Serial.begin(9600);
}

void loop()
{
  Serial.println("Hello");
}
```
@[3](Start using Serial)
@[8](Print "Hello" to serial monitor and create a new line)
---
# Digital Input
---
## digitalRead()

```arduino
int buttonPin = 2;
int buttonState;

void setup(){
    Serial.begin(9600);
}

void loop(){
    buttonState = digitalRead(buttonPin);
    Serial.println(buttonState);
}
```
---
# Conditionals

Conditional statements make decisions on what to do
---
# if

*if* something is true *then* perform an action

```arduino
int buttonPin = 2;
int buttonState;

void setup(){
    Serial.begin(9600);
}

void loop(){
    buttonState = digitalRead(buttonPin);
    
    if (buttonState == 1){
        Serial.println("You pushed the button!");
    }
}
```
---
*if* something is true *then* perform an action

*otherwise* do something else

```arduino
int buttonPin = 2;
int buttonState;

void setup(){
    Serial.begin(9600);
}

void loop(){
    buttonState = digitalRead(buttonPin);
    
    if (buttonState == 1){
        Serial.println("You pushed the button!");
    }
    else {
        Serial.println("You're not pushing the button :(")
        Serial.println("Push the button and stop making Arduino sad.");
    }
}
```
---
## Try It

Use this to turn an LED on when you press a button and off when you don't
