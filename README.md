# Real-time-environmental-parameter-monitoring-system-using-IoT-and-sensor-network
Built an IoT system to track environmental factors like temperature, humidity, and weather in real time. Simulated the hardware circuit and sensor data processing logic to ensure fast and accurate readings.

#include <DHT.h>
#include<LiquidCrystal_I2C.h>
LiquidCrystal_I2C lcd(0X27,20,4);
#define DHTPIN 2
#define DHTTYPE DHT11
#define BUZZER 9
#define LDR 7
#define RAIN 8

DHT dht(DHTPIN, DHTTYPE);

void setup()
{
  lcd.init();  
  lcd.backlight();
  pinMode(LDR INPUT);
  pinMode(RAIN, INPUT);
  pinMode(BUZZER,OUTPUT);
  dht.begin();
}

void loop()
{
float temp = dht.readTemperature();
float hum = dht.readHumidity();
int a = digitalRead(LDR);
int b = digitalRead(RAIN);
lcd.setCursor(0,0);
lcd.print("T = ");
lcd.print(temp);
lcd.setCursor(0,1);
lcd.print("H = ");
lcd.print(hum);

lcd.setCursor(0,2);
  if(a == LOW)
  {
    lcd.print("Cloudy");
  }
  else
  {
    lcd.print("Sunny");
  }

lcd.setCursor(0,3);
  if(b == LOW)
  {
    digitalWrite(BUZZER,LOW);
    lcd.print("Rainy");
  }
  else
  {
    digitalWrite(BUZZER,HIGH);
    lcd.print("No Rain");
  }

 delay(1000);
}
