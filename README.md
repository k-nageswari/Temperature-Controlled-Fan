# Temperature-Controlled Fan Speed System

This project demonstrates how to control the speed of a fan based on the temperature readings from a DHT11 temperature sensor. The fan speed is controlled via PWM, and the temperature is displayed on a 16x2 LCD screen. The project is built using Arduino and utilizes the DHT11 sensor, a PWM-controlled fan, and an LCD to display the current temperature and fan speed.

## Components Used:
- Arduino (Uno, Nano, etc.)
- DHT11 Temperature & Humidity Sensor
- 16x2 LCD Display (with I2C or parallel connection)
- Fan (with PWM control)
- Jumper wires
- 10k Ohm resistor (optional, for DHT sensor pull-up)

## Libraries Required:
- **DHT sensor library**: To interface with the DHT11 sensor.
- **LiquidCrystal library**: To interface with the LCD screen.

### Library Installation:
1. Go to **Sketch > Include Library > Manage Libraries** in the Arduino IDE.
2. Search for and install the following libraries:
   - `DHT sensor library` by Adafruit
   - `LiquidCrystal` (This is included by default in the Arduino IDE)

## Wiring:
- **DHT11**:
  - Connect VCC to 5V
  - Connect GND to GND
  - Connect the data pin to **digital pin 12** on Arduino (this is defined as `dht_dpin` in the code).
- **LCD Display**:
  - Connect the pins as per the Arduino LCD pinout:
    - RS → Pin 7
    - EN → Pin 6
    - D4 → Pin 5
    - D5 → Pin 4
    - D6 → Pin 3
    - D7 → Pin 2
- **PWM Fan**:
  - Connect the PWM pin to **Pin 9** on Arduino (defined as `pwm` in the code).

## How it Works:
1. The DHT11 sensor continuously reads the temperature.
2. Based on the temperature value, the fan speed is adjusted via PWM:
   - If the temperature is below 26°C, the fan is turned off.
   - If the temperature is between 26°C and 29°C, the fan speed increases in increments (20%, 40%, 60%, 80%).
   - If the temperature exceeds 29°C, the fan runs at full speed (100%).
3. The temperature and fan speed are displayed on a 16x2 LCD screen, along with the current temperature and fan speed percentage.

