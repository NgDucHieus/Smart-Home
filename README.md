# Smart Home Automation

Smart Home Automation goes beyond simple on/off controls by integrating a Real Time Operating System (RTOS) to perform multiple actions simultaneously based on real-time events. This project demonstrates a comprehensive home automation system featuring wireless control, activity monitoring, and automated safety and security measures.

## Features
- Wireless control with Bluetooth
- Dedicated Android app
- Activity monitoring on OLED display and app
- Temperature sensing using DHT11 sensor
- Light intensity sensing using LDR
- Fan/Light control in 3 modes: manual, automatic (based on sensors), and off
- Person detection at door using ultrasonic sensor
- Touch detection on door with alarm using ESP32 inbuilt touch sensor
- Smoke detection with alarm using MQ2 sensor

## Hardware Requirements
- ESP32 Microcontroller
- DHT11 Temperature and Humidity sensor
- LDR module
- MQ2 Gas/Smoke Sensor
- Ultrasonic Sensor
- OLED display
- Relay
- Buzzers
- LEDs
- Bulb
- DC fan

## System Overview
The entire system is custom-made with wiring and placements planned according to requirements, developed to resemble a room in a house.

## Schematic
Components can be assembled and connected as shown in the schematic (provide a link or image to the schematic here).

## Software
### Arduino IDE Setup
1. **Download and install the Arduino IDE**
2. **Install the ESP32 Library**:
   - Go to `File -> Preferences -> Additional Boards Manager URLs` and add: 
     ```
     https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json
     ```
   - Then in `Tools -> Board Manager`, search for `ESP32` and install

### Required Libraries
- Bluetooth Serial
- Wire
- DHT
- Adafruit_SSD1306
- Adafruit_GFX
- Ticker

### Real Time Operating System
- **freeRTOS**: ESP32 supports freeRTOS out of the box in Arduino IDE with its own flavor on top of the original for proper integration.

### Android App
- The Android app is developed on the [MIT App Inventor](http://appinventor.mit.edu/) platform.

## Working
### Connecting to App
- **Connect/Disconnect**: Use the button in the app to connect with the system via Bluetooth. The ESP32 microcontroller has a built-in Bluetooth module.

### Activity Monitoring
- Sensor activity and switch controls are monitored on an OLED display interfaced using the I2C communication protocol. The same is monitored on the Android app.

### Temperature and Light Sensing
- **Temperature**: DHT11 digital sensor senses room temperature and displays it on the App/OLED.
- **Light Intensity**: LDR (Light Dependent Resistor) module senses light intensity for automatic switching of the bulb.

### Safety System
- **Smoke Detection**: MQ2 sensor activates a buzzer and LED in presence of smoke. The buzzer turns off automatically once the smoke disappears.

### Security System
- **Person Detection**: Ultrasonic sensor on the door detects presence, displaying it on the App/OLED and turning on an LED.
- **Touch Detection**: ESP32 inbuilt touch sensor detects touch on the door handle, activating a buzzer and displaying the presence on the App/OLED with an LED indicator. It can be deactivated via the app.

### Fan/Light Control
- **Manual Mode**: Use buttons on the App to manually switch the bulb and fan on/off.
- **Automatic Mode**: 
  - **Fan**: Turns on when temperature exceeds 33°C and off when it falls below.
  - **Bulb**: Turns on/off based on light intensity sensed by LDR.
- **Off Mode**: Switch everything off with one button on the app when leaving the room.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
