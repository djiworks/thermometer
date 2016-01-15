# Simple arduino thermometer
Simple arduino program to display temperature and humidity. DHT 11 and LCD 1602 with I2C were used. The main goal is to learn how to use digital sensor and to display things over a LCD. That way, this project is a very simple homemade thermometer ;)

## Hardware
- Arduino Uno
- DHT11: Simple temperature and humidity sensor (It doesn't seem to be accurate).
- LCD 1602 with I2C: Display 16 characters per line (2 lines available). With the I2C, the LCD just has 4 pins (GND, VCC, SDA and SDL)

## Libraries
- Arduino IDE: https://www.arduino.cc/en/Main/Software
- LiquidCrystal library: https://bitbucket.org/fmalpartida/new-liquidcrystal/downloads. You will not be able to find it directly in the library manager included in Arduino IDE. So, add it using its zip file.
- Adafruit_DHT_Unified / DHT_sensor_library / Adafruit_Unified_Sensor: I use these librairies to make the sensor work. You can easily find them from the IDE

## Circuit
![alt tag](https://raw.githubusercontent.com/djiworks/thermometer_arduino/master/circuit.jpg)

On my sensor, the data pin is the first one from the left. The middle one is +5V and the final one is GND.

To plug SDA/SDL pins of your I2C, you can use SDA/SDL pins of ardunio (2 pins at the top - left) or the analog pins 4 (SDA) and 5 (SCL).
See http://forum.arduino.cc/index.php?topic=84190.0

## Code underline
```
LiquidCrystal_I2C lcd(LCD_ADDR, 2, 1, 0, 4, 5, 6, 7, 3, POSITIVE);
```
This part allow you to configure the right LCD address. Note that other args depends on your I2C plugged on your LCD 1602. I just kept pins I found on the net.
To find the rigth LCD_ADDR, I suggest you to run I2C scanner on your circuit: see http://www.instructables.com/id/I2C-LCD-Controller-the-easy-way/?ALLSTEPS#step4
