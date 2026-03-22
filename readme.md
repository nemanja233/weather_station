# ESP8266 Weather Station

A small weather station using **ESP8266**, **DHT22**, and an **OLED display**. Shows temperature, humidity, and a 3-day forecast from OpenWeatherMap. Supports remote monitoring via **RemoteXY**.  

---

## Hardware

- **ESP8266** (NodeMCU or Wemos D1 Mini)  
- **DHT22 sensor**  
- **128x64 SH1106 OLED display**  
- **LEDs** (optional) for air quality indicator  

**Wiring:**

- **OLED Display** → D1 (SCL), D2 (SDA)  
- **DHT22** → D5  
  - DATA pin connected to D5  
  - 10kΩ pull-up resistor between **VCC** and **DATA**  

Optional LEDs for air quality:

- Green → D7  
- Yellow → D8  
- Red → D6  

---

## Software / Libraries

Make sure you have these libraries installed in Arduino IDE:

- [U8g2](https://github.com/olikraus/u8g2) – for OLED  
- [DHT sensor library](https://github.com/adafruit/DHT-sensor-library)  
- [ArduinoJson](https://arduinojson.org/) – for parsing OpenWeatherMap API  
- [ESP8266HTTPClient](https://github.com/esp8266/Arduino)  
- [RemoteXY](https://remotexy.com/en/) – for remote monitoring  

---

## Setup

1. Open the `.ino` file in Arduino IDE.  
2. Set your WiFi credentials:

```cpp
#define REMOTEXY_WIFI_SSID "YOUR_SSID"
#define REMOTEXY_WIFI_PASSWORD "YOUR_PASSWORD"
```

3. Set your OpenWeatherMap API key, city, and country:

```cpp
#define OWM_API_KEY   "YOUR_API_KEY"
#define OWM_CITY      "CITY"
#define OWM_COUNTRY   "COUNTRY"
```

4. Connect the hardware according to the wiring section above.  
5. Upload the code to the ESP8266.  
6. Open Serial Monitor to check WiFi and API connection.  
7. Monitor temperature/humidity on the OLED and RemoteXY app.  

---

## Features

- **Local OLED display** shows current temperature and humidity.  
- **3-day forecast** from OpenWeatherMap (temperature + weather).  
- **Air quality LEDs** based on temperature and humidity:  
  - Green → comfortable  
  - Yellow → caution  
  - Red → poor  
- **Remote monitoring** via RemoteXY app.  
- **Graph** of temperature/humidity over time (OLED + RemoteXY).  

---

## OpenWeatherMap Integration

The project fetches weather forecast data via OpenWeatherMap API:

- Fetch interval: 10 minutes (`600000 ms`)  
- Forecast stored for 3 days  
- Supports standard weather descriptions: Clear, Rain, Clouds, Snow, Drizzle  

**API settings in code:**

```cpp
#define OWM_API_KEY   "YOUR_API_KEY"
#define OWM_CITY      "CITY"
#define OWM_COUNTRY   "COUNTRY"
#define OWM_FETCH_INTERVAL  600000UL
#define FORECAST_DAYS 3
```

---

## Screens

The OLED display cycles every 5 seconds:

1. **Current temperature/humidity**  
2. **Temperature graph**  
3. **3-day weather forecast**  

---

## Notes

- Make sure the **10kΩ pull-up resistor** is installed for DHT22 DATA pin.  
- LEDs are optional but useful for air quality indicator.  
- RemoteXY requires a mobile app to view graphs and LEDs remotely.  
- OpenWeatherMap API key must be valid for forecast feature to work.  

---

## License

Open Source