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
Our project does not require an Arduino to run. However, we have a JSON file instead for the coding of the alexa skill.
```
{
    "interactionModel": {
        "languageModel": {
            "invocationName": "my coffee machine",
            "intents": [
                {
                    "name": "AMAZON.CancelIntent",
                    "samples": [
                        "Alexa stop the coffee"
                    ]
                },
                {
                    "name": "AMAZON.HelpIntent",
                    "samples": []
                },
                {
                    "name": "AMAZON.StopIntent",
                    "samples": []
                },
                {
                    "name": "AMAZON.NavigateHomeIntent",
                    "samples": []
                },
                {
                    "name": "CoffeeControl",
                    "slots": [
                        {
                            "name": "coffee_size",
                            "type": "coffee_size"
                        },
                        {
                            "name": "coffee_type",
                            "type": "coffee_type"
                        }
                    ],
                    "samples": [
                        "Alexa can I have a {coffee_size} {coffee_type} coffee from my coffee machine",
                        "Alexa I want a {coffee_size} {coffee_type} coffee",
                        "Alexa give me a cup of {coffee_size} {coffee_type} coffee",
                        "Alexa give me a {coffee_size} {coffee_type} coffee",
                        "I would like a {coffee_size} {coffee_type} coffee"
                    ]
                },
                {
                    "name": "AMAZON.PauseIntent",
                    "samples": []
                },
                {
                    "name": "AMAZON.ResumeIntent",
                    "samples": []
                },
                {
                    "name": "AMAZON.MoreIntent",
                    "samples": []
                },
                {
                    "name": "AMAZON.NavigateSettingsIntent",
                    "samples": []
                },
                {
                    "name": "AMAZON.NextIntent",
                    "samples": []
                },
                {
                    "name": "AMAZON.PageUpIntent",
                    "samples": []
                },
                {
                    "name": "AMAZON.PageDownIntent",
                    "samples": []
                },
                {
                    "name": "AMAZON.PreviousIntent",
                    "samples": []
                },
                {
                    "name": "AMAZON.ScrollRightIntent",
                    "samples": []
                },
                {
                    "name": "AMAZON.ScrollDownIntent",
                    "samples": []
                },
                {
                    "name": "AMAZON.ScrollLeftIntent",
                    "samples": []
                },
                {
                    "name": "AMAZON.ScrollUpIntent",
                    "samples": []
                }
            ],
            "types": [
                {
                    "name": "coffee_size",
                    "values": [
                        {
                            "name": {
                                "value": "large",
                                "synonyms": [
                                    "big",
                                    "large size",
                                    "twelve ounce",
                                    "large-sized"
                                ]
                            }
                        },
                        {
                            "name": {
                                "value": "small",
                                "synonyms": [
                                    "small sized",
                                    "small size",
                                    "eight ounce"
                                ]
                            }
                        }
                    ]
                },
                {
                    "name": "coffee_type",
                    "values": [
                        {
                            "name": {
                                "value": "cream",
                                "synonyms": [
                                    "milk coffee",
                                    "coffee with some cream",
                                    "coffee with half-and-half",
                                    "not black coffee",
                                    "coffee with cream"
                                ]
                            }
                        },
                        {
                            "name": {
                                "value": "black",
                                "synonyms": [
                                    "pure coffee",
                                    "coffee",
                                    "just black coffee",
                                    "coffee without cream",
                                    "coffee with no cream"
                                ]
                            }
                        }
                    ]
                }
            ]
        }
    }
}
```
#### Python Code:
#### Results:
The coffee carafe will be turned on at user’s command. For example, when the user says: “Alexa, can I have a small coffee”, the motor will release the knob and pour 8 ounces of coffee in their mug. As for right now, there are 2 valid commands for this program: small or large.
#### Future Work:
As the problem indicated, this project is to serve as a gateway as to explore the possibility to control coffee machines remotely. There are many improvements that can be done in order to make this more practical, such as connecting the coffee device directly to the shop’s POS (Point of Sales) system, making the orders more efficient. Such device can also be used on milk or other beverages since consistency is very important for a coffee shop.
#### License
Copyright <2019> <Fangji Large>
Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:
 
The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.
 
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

