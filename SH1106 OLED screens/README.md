# SH1106 OLDED Screen 

### Pinout for Arduino Uno
1. VCC -> 5V
2. GND -> GND
3. SDA -> A4
4. SCL -> A5
**Note: There are SDA and SCL pins on arduino UNO do not use them they do not work**

### Pinout for ESP32 
1. VCC -> 3.3V
2. GND -> GND
3. SDA -> D21
4. SCL -> D22

### Libraries
1. Install the Adafruit GFX Library
2. Install the Adafruit SH110X Library 
    - **Note DO NOT INSTALL THE SH1306 LIBRARY IT DOES NOT WORK UNLESS YOU ARE RUNNING A OLED SCREEN THAT IS BASED ON SH1306**
You can alternativly used the lcdgfx library that one also seems to work but is more complicated. 


### Sample code
The Provided Sample code does not work so instead use this
```#include <SPI.h>
#include <Wire.h>
#include <Adafruit_GFX.h>
#include <Adafruit_SH110X.h>
Adafruit_SH1106G display = Adafruit_SH1106G(128, 64, &Wire);
void setup() {
  // put your setup code here, to run once:
  display.begin(0x3c, true); // Address 0x3C default you might need to change this depending on the board
  display.clearDisplay();
  display.display();
  display.setTextSize(1);
  display.setTextColor(SH110X_WHITE);
}

void loop() {
  for (double i = 0; i < 50; ++i) {
    display.clearDisplay();
    display.setCursor(55, 32);
    display.println(i);
    display.display(); 
    delay(500); 
  }
}```

This should cycle through doubles make sure it works 