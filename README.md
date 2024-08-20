# Smart Thermostat for Air Conditioner - IoT Project

## About this Project

This IoT project allows users to remotely control the temperature and power state of their existing air conditioners without modifying the A/C control unit, making it a non-invasive and safe solution. The goal is to help users save energy in the long run. The project is based on the Arduino IoT Cloud service, utilizing an ESP-32 development board. The code includes Alexa-compatible variables, enabling control via Amazon Alexa.

The ESP-32's dual-core CPU provides the flexibility to run two separate loops simultaneously, allowing for uninterrupted user inputs while managing and controlling the A/C's state. The board's multiple analog inputs are ideal for reading data from various sensors.

One core of the ESP-32 handles cloud services and user inputs, while the other core is responsible for controlling the A/C based on user-set values. Note that the code includes variables for controlling other devices, which are not covered in this section.

## Operation

To control the A/C, the project uses IR remote commands. The NEC protocol is used to obtain the necessary IR codes from the A/C remote via the serial monitor with the IRremote_command code. Only the power button code is needed for this setup. The A/C's temperature is set to its lowest, as the ESP-32 externally monitors and controls the temperature.

The ESP-32 utilizes a photoresistor, IR LED, and DHT11 sensors to control the A/C based on the set temperature. The photoresistor detects the A/C's power state by observing the power LED. If the A/C needs to be turned on or off, the IR LED sends the appropriate NEC command. The DHT11 sensor reads the room temperature, and the ESP-32 sends commands through the IR LED to turn the A/C on or off based on the room temperature relative to the set temperature.

All necessary information is displayed on an LCD, and the board includes push-buttons for local A/C control.

## Technical Sheet

The following components were utilized in this project. For wiring details, please refer to each component's datasheet.

- ESP-32 Development Board
- DHT11 Humidity and Temperature Sensor
- Liquid Crystal Display (LCD)
- IR LED
- IR Receiver Module
- Photoresistor
- Push-buttons
- PCB Prototype Board
