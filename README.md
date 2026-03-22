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
Live graph (last values)
🔵 Screen 2 – Forecast
3-day forecast
Min / Max temperature
Weather icons (sun, cloud, rain)
📱 RemoteXY App
Displays:
Temperature graph
Humidity graph
Air quality LEDs
Connect via WiFi on port 6377
🚦 Air Quality Logic
Condition	LED
Good (18–24°C, 35–60%)	🟢 Green
Medium	🟡 Yellow
Bad	🔴 Red
📡 Weather Forecast
Source: OpenWeatherMap API
Updates every 10 minutes
Uses JSON parsing with filtering (efficient memory usage)
Shows:
Day (Mon, Tue, …)
Min/Max temperature
Weather condition
📊 Graph System
OLED graph width: 128 points
Auto-scrolling
Maps temperature dynamically
🔄 Timing
Sensor read: every 1 second
Screen switch: every 5 seconds
Forecast update: every 10 minutes
⚠️ Important Notes
Use 3.3V ONLY (ESP8266 is NOT 5V safe)
DHT22 must have pull-up resistor
I2C pins are fixed:
D1 → SCL
D2 → SDA
Make sure WiFi connects before API calls
🖼️ UI Features
Custom icons (weather + system)
Smooth graph rendering
Multi-screen interface
Loading / fetching animation
🔧 Future Improvements
🌈 Better icons / animations
📅 5-day forecast
🔋 Battery + deep sleep
🌍 Web dashboard
📈 Data logging (SD / cloud)
📄 License

Open-source – free to use and modify.

🙌 Credits
U8g2 Library
ArduinoJson
OpenWeatherMap API
RemoteXY
⭐ Project Status

✔ Fully working
✔ Optimized memory usage
✔ Stable WiFi + API
