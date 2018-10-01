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
@[7](Print "Hello" to serial monitor and create a new line)
---
# Digital Input
---
## digitalRead()

int buttonPin = 2;
int buttonState;

void setup(){
    Serial.begin(9600);
}

void loop(){
    buttonState = digitalRead(buttonPin);
    Serial.println(buttonState);
}
---
## Try It

Use this to turn an LED on when you press a button and off when you don't
