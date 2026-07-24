# Real-time-environmental-parameter-monitoring-system-using-IoT-and-sensor-network
Built an IoT system to track environmental factors like temperature, humidity, and weather in real time. Simulated the hardware circuit and sensor data processing logic to ensure fast and accurate readings.
{
  "version": 1,
  "author": "Candice hephzibah. S",
  "editor": "wokwi",
  "parts": [
    { "type": "wokwi-arduino-uno", "id": "uno", "top": 0, "left": 0, "attrs": {} },
    { "type": "wokwi-dht22", "id": "dht1", "top": -124.5, "left": -111, "attrs": {} },
    {
      "type": "wokwi-buzzer",
      "id": "bz1",
      "top": -93.6,
      "left": 299.4,
      "attrs": { "volume": "0.1" }
    },
    {
      "type": "wokwi-photoresistor-sensor",
      "id": "ldr1",
      "top": 214.4,
      "left": -8.8,
      "attrs": {}
    },
    { "type": "wokwi-potentiometer", "id": "pot1", "top": 104.3, "left": 345.4, "attrs": {} },
    {
      "type": "wokwi-lcd2004",
      "id": "lcd1",
      "top": -272,
      "left": -23.2,
      "attrs": { "pins": "i2c" }
    }
  ],
  "connections": [
    [ "dht1:VCC", "uno:3.3V", "red", [ "v0" ] ],
    [ "dht1:SDA", "uno:2", "green", [ "v0" ] ],
    [ "dht1:GND", "uno:GND.2", "black", [ "v0" ] ],
    [ "pot1:GND", "uno:GND.3", "black", [ "v0" ] ],
    [ "pot1:SIG", "uno:A0", "green", [ "v0" ] ],
    [ "pot1:VCC", "uno:VIN", "red", [ "v0" ] ],
    [ "bz1:2", "uno:9", "green", [ "v0" ] ],
    [ "bz1:1", "uno:GND.3", "green", [ "v0" ] ],
    [ "ldr1:VCC", "uno:5V", "red", [ "h0" ] ],
    [ "ldr1:GND", "uno:GND.3", "black", [ "h0" ] ],
    [ "ldr1:DO", "uno:7", "green", [ "h0" ] ],
    [ "lcd1:GND", "uno:GND.1", "black", [ "h0" ] ],
    [ "lcd1:VCC", "uno:5V", "red", [ "h0" ] ],
    [ "lcd1:SDA", "uno:A4.2", "green", [ "h0" ] ],
    [ "lcd1:SCL", "uno:A5.2", "green", [ "h0" ] ]
  ],
  "dependencies": {}
}
