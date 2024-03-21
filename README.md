###  DATE: 21.03.2024

###  NAME: Dharshini DS
###  ROLL NO : 212221230022
###  DEPARTMENT: AI-DS

# Experiment-no-6-DC-Motor-Speed-Control-Using-Arduino

### AIM : 

To control the speed and the direction of a DC motor using L293D driver ic( H- bridge)

### Components Required:

•	Arduino UNO board
•	L293D driver
•	12V DC motor
•	10K ohm potentiometer
•	Pushbutton
•	12V source
•	Breadboard
•	Jumper wires

### THEORY 

The L293D quadruple half-H drivers chip allows us to drive 2 motors in both directions, with two PWM outputs from the Arduino we can easily control the speed as well as the direction of rotation of one DC motor. (PWM: Pulse Width Modulation).
Arduino DC motor control circuit:
Project circuit schematic diagram is the one below.

![image](https://user-images.githubusercontent.com/36288975/167763051-b230c183-afc5-46f2-ba95-0f95e10dd6c9.png)
FIGURE-01 H BRIDGE CIRUCIT INTERFACE 
 
The speed of the DC motor (both directions) is controlled with the 10k potentiometer which is connected to analog channel 0 (A0) and the direction of rotation is controlled with the push button which is connected to pin 8 of the Arduino UNO board. If the button is pressed the motor will change its direction directly.
The L293D driver has 2 VCCs: VCC1 is +5V and VCC2 is +12V (same as motor nominal voltage). Pins IN1 and IN2 are the control pins where:
![image](https://user-images.githubusercontent.com/36288975/167763120-1421c2c5-8381-49eb-b376-03f6e1113b7a.png)
TABLE-01 EXITATION TABLE FOR H BRIDGE 

As shown in the circuit diagram we need only 3 Arduino terminal pins, pin 8 is for the push button which toggles the motor direction of rotation. Pins 9 and 10 are PWM signal outputs, at any time there is only 1 active PWM, this allows us to control the direction as well as the speed by varying the duty cycle of the PWM signal. The active PWM pin decides the motor direction of rotation (one at a time, the other output is logic 0).

### PROGRAM 
```
int enable = 2;
int input1 = 3;
int input2 = 4;


void setup()
{
  pinMode(enable, OUTPUT);
  pinMode(input1, OUTPUT);
  pinMode(input2, OUTPUT);
}

void loop()
{
  digitalWrite(enable, 255);
  delay(1000); 
  digitalWrite(input1, HIGH);
  digitalWrite(input2, LOW);
  delay(7000);
  digitalWrite(input1, LOW);
  digitalWrite(input2, HIGH);
  delay(7000);

}
```
### OUTPUT


![533ex6j](https://github.com/Dharshini-DS/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/93427345/5d14e8a8-41ee-40fe-917d-1016118aa1d6)


![533ex6k](https://github.com/Dharshini-DS/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/93427345/173695a2-f8a6-41c6-aea3-7faccfa1fd91)


### GRAPH AND TABULATION 


![533ex6](https://github.com/Dharshini-DS/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/93427345/df9aab9e-b468-4a50-bf0b-c8ef3309b3c6)


![533ex6i](https://github.com/Dharshini-DS/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/93427345/15e0b7ef-b375-47a9-8b1c-b70f13ac07f6)


### RESULTS AND DISCUSSION 
Arduino uno interfacing with DC motor is learned and controled clock wise and anti clock wise by using PWM signal.
