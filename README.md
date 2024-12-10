# Smart-Study-Desk


## Overview

The Smart Study Desk is designed to enhance your study experience by integrating sensors, lighting control, and automated drawer actions. The desk detects your presence, adjusts the lighting based on ambient light levels, and opens a drawer automatically for 10 seconds. It also tracks the time you spend at the desk and displays it on a 7-segment display.

This version of the project uses the **ESP32** microcontroller instead of an Arduino Uno. The ESP32 brings Wi-Fi and Bluetooth capabilities, along with a larger number of I/O pins, which is beneficial for future extensions.

## Features

1. **Presence Detection**: Detects if a person is near the desk using a PIR sensor.
2. **Automatic Lighting Adjustment**: Measures ambient light using an LDR and turns on a lamp if the light intensity is low.
3. **Automatic Drawer Operation**: Opens the desk drawer for 10 seconds upon detecting a person.
4. **Time Tracking**: Displays the time spent at the desk (in seconds) on a 7-segment display.

## Hardware Components

- **ESP32** (any variant with enough I/O pins, such as ESP32 DevKit v1)
- **PIR Sensor**: For detecting motion
- **LDR (Light Dependent Resistor)**: For measuring ambient light
- **Relay Module**: To control the lamp
- **Servo Motor**: To open/close the drawer
- **7-Segment Display**: To show the time spent at the desk
- **Jumper Wires** and **Breadboard** for prototyping

## Wiring Diagram

You can create and attach a schematic or circuit diagram as a `.pdf` file in the `hardware` folder.

## Software

The code is written for the **ESP32** using the Arduino IDE. You can upload the provided code to an ESP32 board to control the system.

### Arduino Code
The main code for this project is in the `smart_desk_esp32.ino` file located in the `code` folder.

### Libraries
- **Servo** library (included by default in the Arduino IDE)
- **SevSeg** (if using a 7-segment display library)

## Setup

### Step 1: Install the Arduino IDE

Download and install the [Arduino IDE](https://www.arduino.cc/en/software) if you haven't already.

### Step 2: Install ESP32 Board in Arduino IDE

1. Open Arduino IDE.
2. Go to **File > Preferences** and in the "Additional Boards Manager URLs" field, add the following URL:  
   `https://dl.espressif.com/dl/package_esp32_index.json`
3. Go to **Tools > Board > Boards Manager** and search for **ESP32**.
4. Install the **esp32 by Espressif Systems** package.

### Step 3: Wire the Components

- **PIR Sensor**: Connect to **GPIO 13** (or any free digital pin on ESP32).
- **LDR**: Connect one leg to **3.3V** and the other leg to **GPIO 34** (Analog input).
- **Relay**: Connect the relay control pin to **GPIO 12**.
- **Servo Motor**: Connect the control pin to **GPIO 14**.
- **7-Segment Display**: Connect the display pins to available **GPIOs** (e.g., GPIOs 15-19).

### Step 4: Upload the Code

1. Open the Arduino IDE.
2. Select your ESP32 board under **Tools > Board** (e.g., "ESP32 Dev Module").
3. Select the correct **Port** under **Tools > Port**.
4. Click the **Upload** button to upload the code to your ESP32.

### Step 5: Power On

Once the code is uploaded, power on your ESP32 and connect your components. The system will detect your presence and function as described.
