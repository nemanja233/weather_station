ESP8266 Weather & Environment Monitor

This project uses an ESP8266 to monitor temperature and humidity with a DHT22 sensor, display data on an OLED screen, control LEDs based on conditions, and remotely monitor graphs via RemoteXY. It also fetches weather forecasts from OpenWeatherMap.

Features
Reads temperature and humidity from DHT22
Displays live data on a 128x64 OLED
Controls LEDs to indicate air quality:
Green: Good
Yellow: Moderate
Red: Poor
Sends live data to RemoteXY graphs
WiFi connectivity for remote monitoring
Fetches 3-day weather forecast from OpenWeatherMap:
Shows min/max temperature
Weather condition (Clear, Rain, Clouds, Snow, etc.)
Hardware
Component	Pin / Connection
ESP8266	-
DHT22	D5 (with 10kΩ pull-up between VDD and DATA)
OLED 128x64	I2C (SDA = D2, SCL = D1)
LED Red	D6
LED Green	D7
LED Yellow	D8
Software / Libraries
DHT sensor library
U8g2 OLED library
RemoteXY
ArduinoJson (for parsing OpenWeatherMap JSON)
ESP8266WiFi
Usage
Install required libraries in Arduino IDE.
Open the project .ino file.

Set your WiFi credentials in the code:

#define REMOTEXY_WIFI_SSID "YOUR_SSID"
#define REMOTEXY_WIFI_PASSWORD "YOUR_PASSWORD"

Set your OpenWeatherMap API key, city, and country:

#define OWM_API_KEY   "YOUR_API_KEY"
#define OWM_CITY      "CITY"
#define OWM_COUNTRY   "COUNTRY"
Connect the hardware as shown in the Hardware table.
Upload the code to the ESP8266.
Open the Serial Monitor to check the WiFi connection.
Monitor temperature/humidity on the OLED or remotely via RemoteXY.
The OLED will display a 3-day forecast fetched from OpenWeatherMap.
LED Indicators
Green LED – Comfortable temperature & humidity
Yellow LED – Moderate / warning
Red LED – Poor / extreme conditions
RemoteXY
Graphs show live temperature and humidity trends
LED status mirrors physical LEDs
Works over local WiFi network
OpenWeatherMap Forecast
Fetches weather data every 10 minutes (OWM_FETCH_INTERVAL = 600000UL)
Displays:
Day of the week
Min/Max temperature
Weather condition icon
Icons supported: Clear, Rain, Clouds, Snow, Drizzle
License

This project is open-source. Feel free to copy, modify, and use it in your own projects.

Author

Nemanja Stojadinovic
