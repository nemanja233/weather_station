# 🌦️ ESP8266 Smart Weather Station

**DHT22 + OLED (SH1106) + WiFi Forecast + RemoteXY + LED Air Quality**

A fully featured weather station built with an **ESP8266 (NodeMCU)** that displays real-time environmental data on an OLED screen, fetches a **3-day weather forecast**, and provides both **local and remote visualization** via the RemoteXY app.

---

## 🚀 Features

- 🌡️ Real-time **Temperature & Humidity** (DHT22)  
- 📊 **Live temperature graph** on OLED  
- 📡 **3-day weather forecast** (OpenWeatherMap API)  
- 🖥️ OLED UI with **icons & multiple screens**  
- 📱 **RemoteXY app integration**  
- 🚦 **Air quality indicator** (LED system)  
- 🔄 Automatic **screen switching**  
- 🌐 **WiFi-enabled**  

---

## 🧰 Hardware

- ESP8266 (NodeMCU)  
- DHT22 sensor  
- OLED Display (SH1106, 128x64, I2C)  
- 10kΩ resistor (pull-up)  
- 3x LEDs (Red, Yellow, Green)  
- Breadboard + jumper wires  

---

## 🔌 Wiring

### 📺 OLED Display (I2C)

| Pin | Connection |
|-----|-----------|
| VCC | 3.3V |
| GND | GND |
| SCL | D1 (GPIO5) |
| SDA | D2 (GPIO4) |

---

### 🌡️ DHT22 Sensor

| Pin | Connection |
|-----|-----------|
| VDD | 3.3V |
| GND | GND |
| DATA | D5 (GPIO14) |

👉 **Important:**  
Use a **10kΩ pull-up resistor** between **VDD** and **DATA**

---

### 🚦 LEDs (Air Quality Indicator)

| LED | Pin |
|-----|-----|
| 🟢 Green | D7 |
| 🟡 Yellow | D8 |
| 🔴 Red | D6 |

---

## 📚 Libraries

```cpp
#include <U8g2lib.h>
#include "DHT.h"
#include <ArduinoJson.h>
#include <ESP8266HTTPClient.h>
#include <WiFiClient.h>
#include <ESP8266WiFi.h>
#include <RemoteXY.h>
```

⚙️ Configuration
🌐 WiFi (RemoteXY)
    #define REMOTEXY_WIFI_SSID "YOUR_SSID"
    #define REMOTEXY_WIFI_PASSWORD "YOUR_PASSWORD"
🌦️ OpenWeatherMap API
    #define OWM_API_KEY   "YOUR_API_KEY"
    #define OWM_CITY      "YOUR_CITY"
    #define OWM_COUNTRY   "YOUR_COUNTRY"
🖥️ Display Modes
🟢 Screen 1 – Local Data
    Temperature
    Humidity
    Live graph (recent values)
🔵 Screen 2 – Forecast
    3-day forecast
    Min / Max temperature
    Weather icons (☀️ ☁️ 🌧️)
📱 RemoteXY App connection
  

🙌 Credits
📚 U8g2 Library
🧩 ArduinoJson
🌦️ OpenWeatherMap API
📱 RemoteXY
⭐ Project Status
✔ Fully working
✔ Optimized memory usage
✔ Stable WiFi & API integration

💡 A compact yet powerful IoT weather station combining local sensing, cloud data, and remote monitoring in one project.




