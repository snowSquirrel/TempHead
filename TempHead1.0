#include "DHT.h"
#include <Wire.h>
#include "Adafruit_LEDBackpack.h"
#include "Adafruit_GFX.h"

#define DHTPIN 2     // what digital pin we're connected to
#define DHTTYPE DHT22   // DHT 22  (AM2302), AM2321

DHT dht(DHTPIN, DHTTYPE);
Adafruit_AlphaNum4 alpha4 = Adafruit_AlphaNum4();

void setup() {
  Serial.begin(9600);
  Serial.println("DHTxx test!");

  dht.begin();
  alpha4.begin(0x70);
}

void loop() {
  // Wait a few seconds between measurements.
  delay(500);

    // Read temperature as Celsius (the default)
  float t = dht.readTemperature();
  // Read temperature as Fahrenheit (isFahrenheit = true)
  float f = dht.readTemperature(true);

  // Check if any reads failed and exit early (to try again).
  if (isnan(t) || isnan(f)) {
    Serial.println("Failed to read from DHT sensor!");
    return;
  }

  Serial.print("Temperature: ");
  Serial.print(t);
  Serial.print(" *C ");
  Serial.print(f);
  Serial.print(" *F\t");
  
alpha4.setBrightness(0);  
//alpha4.clear();  
alpha4.writeDigitAscii(0, 'F');
alpha4.writeDisplay(); 

if(f < 90 && f >= 80){
 alpha4.writeDigitAscii(2, '8');
 alpha4.writeDisplay(); 
 int xEighty = f - 80;
 alpha4.writeDigitAscii(3, '0'+ xEighty);
 alpha4.writeDisplay(); 
}
if(f < 80 && f >= 70){
 alpha4.writeDigitAscii(2, '7');
 alpha4.writeDisplay();
 int xSeventy = f - 70;
 alpha4.writeDigitAscii(3, '0'+ xSeventy);
 alpha4.writeDisplay(); 
}
if(f < 70 && f >= 60){
 alpha4.writeDigitAscii(2, '6');
 alpha4.writeDisplay();
int xSixty = f - 60;
 alpha4.writeDigitAscii(3, '0'+ xSixty);
 alpha4.writeDisplay();
}
if(f < 60 && f >= 50){
 alpha4.writeDigitAscii(2, '5');
 alpha4.writeDisplay();
 int xFifty = f - 50;
 alpha4.writeDigitAscii(3, '0'+ xFifty);
 alpha4.writeDisplay(); 
}
if(f < 50 && f >= 40){
 alpha4.writeDigitAscii(2, '4');
 alpha4.writeDisplay();
 int xForty = f - 40;
 alpha4.writeDigitAscii(3, '0'+ xForty);
 alpha4.writeDisplay(); 
}
if(f < 40 && f >= 30){
 alpha4.writeDigitAscii(2, '3');
 alpha4.writeDisplay();
 int xThirty = f - 30;
 alpha4.writeDigitAscii(3, '0'+ xThirty);
 alpha4.writeDisplay(); 
}
if(f < 30 && f >= 20){
 alpha4.writeDigitAscii(2, '2');
 alpha4.writeDisplay();
 int xTwenty = f - 20;
 alpha4.writeDigitAscii(3, '0'+ xTwenty);
 alpha4.writeDisplay(); 
}
if(f < 20 && f >= 10){
 alpha4.writeDigitAscii(2, '1');
 alpha4.writeDisplay();
 int xTen = f - 10;
 alpha4.writeDigitAscii(3, '0'+ xTen);
 alpha4.writeDisplay(); 
}
if(f < 10 && f >= 0){
int xSingle = f;
 alpha4.writeDigitAscii(3, '0'+ xSingle);
 alpha4.writeDisplay(); 
}
if(f < 0 && f >= -9){
 alpha4.writeDigitAscii(2, '-');
 int xNegSingle = f;
 alpha4.writeDigitAscii(3, '0'+ xNegSingle);
 alpha4.writeDisplay();  
}
if(f < -10 && f >= -20){
 alpha4.writeDigitAscii(1, '-');
 alpha4.writeDigitAscii(2, '1');
 alpha4.writeDisplay();
 int xNegTwenty = f + 10;
 alpha4.writeDigitAscii(3, '0'+ xNegTwenty);
 alpha4.writeDisplay();  
}
delay(200);  
}
