# “Alexa Latte” – Voice Controlled Coffee Server

## Problem Statement
Our group project, Alexa Latte, is an attempt to create a device which will dispenses coffee from a commercial carafe on voice command. This project itself doesn’t really provide much practicality since turning a knob is much easier by hand. Rather, this project serves as a gateway as to explore the possibility to control coffee machines remotely.
## Hardware Setup
### Bill of materials
|Part Name          |Purpose           |Price            |
|--------------------|:-------------------|-------------------|
|Amazon Echo Dot            |Receives voice commands from human            |N/A (borrowed from Fang)         |
|    Amazon Smart Outlet        |   Receives commands from Amazon cloud         |     Unknown(purchased by PCC Engineering Department     |
|       Breadboard Power Supply    |       Convert 110V to 5V for the command signal     |    N/A (borrowed from PCC)       |
|Adafruit Motor Hat|                Supply power to the motor      |N/A (borrowed from PCC)     
|      Raspberry Pi      |    Execute the Python codes        |N/A (borrowed from PCC)|
|      Mercury Stepper Motor      |     Turns the carafe’s on/off knob      |      N/A (borrowed from PCC)     |
|       Coffee Carafe     |       Contains coffee     |       N/A (borrowed from PCC)    |
|   Various wires and connectors         |      Connect components together      |   N/A (borrowed from group members and PCC)  |
#### Hookup Guide

|Part	|Pin	|Connector|	Pin	|Part|
|------------|:---|---|---|---|
|Echo Dot|	-	|Micro USB|	-	|Wall outlet|
|Smart Plug|	-|	Micro USB|	DC-in	|Breadboard Power Supply|
|Breadboard Power Supply|	3v3	|Female-male jumper wire	|#23|	Raspberry Pi|
|Raspberry Pi	|All GPIO	|2x20 connector|	All GPIO	|Adafruit motor hat|
|Raspberry Pi|	Ethernet port|	Ethernet cable	|Ethernet port	|Laptop|
|Adafruit motor hat|	5-12v motor power	|Power cord	|-|	Wall outlet|
|Adafruit motor hat	|M1 and M2|	Jumper wires|	-	|Mercury Stepper Motor|
|Mercury Stepper Motor|	-	|Paracord or rope|	Knob	|Coffee carafe|
#### Hardware Schematic:
![](images/Picture1.png)

#### Images:
![](images/Picture2.png)
![](images/Picture3.png)
![](images/Picture4.png)
![](images/Picture5.png)
#### Arduino Code:
Our project does not require an Arduino to run. However, a list of how we set up the voice commands part will be provided:
#### Python Code:
#### Results:
The coffee carafe will be turned on at user’s command. For example, when the user says: “Alexa, can I have a small coffee”, the motor will release the knob and pour 8 ounces of coffee in their mug. As for right now, there are 2 valid commands for this program: small or large.
#### Future Work:
As the problem indicated, this project is to serve as a gateway as to explore the possibility to control coffee machines remotely. There are many improvements that can be done in order to make this more practical, such as connecting the coffee device directly to the shop’s POS (Point of Sales) system, making the orders more efficient. Such device can also be used on milk or other beverages since consistency is very important for a coffee shop.

