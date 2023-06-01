---
layout: post
title: ESP32 IoT webserver & client
author: [Richard Kuo]
category: [Lecture]
tags: [jekyll, ai]
---

.

---
## ESP32 IoT webserver & client


### 應用功能說明
1. 感測溫濕度

### 系統方塊圖

![](https://github.com/tingwei1103/MCU-project/blob/main/images/iot.png?raw=true)


### 圖片

1.HTU21

![](https://github.com/tingwei1103/MCU-project/blob/main/images/64483.jpg?raw=true)

---
2.DHT22


![](https://github.com/tingwei1103/MCU-project/blob/main/images/106571.jpg?raw=true)

### 程式碼

#include <WiFi.h>
#include <WiFiClient.h>
#include <HTTPClient.h>
#include <Wire.h>
#include <Adafruit_HTU21DF.h>

// Connect Vin to 3-5VDC
// Connect GND to ground
// Connect SCL to I2C clock pin (A5 on UNO, D1 on NodeMCU)
// Connect SDA to I2C data pin (A4 on UNO, D2 on NodeMCU)

Adafruit_HTU21DF htu = Adafruit_HTU21DF();

const char* ssid     = "Free Wi-Fi";
const char* password = "0901086625";
String      webserverIP = "http://192.168.1.12"; // Your Webserver IP address

void setup() {
  Serial.begin(115200);
  Serial.println("HTU21D-F test");  
  if (!htu.begin()) {
    Serial.println("Couldn't find HTU21DF sensor!");
    while (1);
  }
  
  // We start by connecting to a WiFi network
  Serial.println();
  Serial.println();
  Serial.print("Connecting to ");
  Serial.println(ssid);
  
  WiFi.begin(ssid, password);
  
  while (WiFi.status() != WL_CONNECTED) {
    delay(500);
    Serial.print(".");
  }

  Serial.println("");
  Serial.println("WiFi connected");  
  Serial.println("IP address: ");
  Serial.println(WiFi.localIP());
}

void loop() {
  delay(5000);

  float temp  = htu.readTemperature();
  float humid = htu.readHumidity();
  Serial.print(temp);
  Serial.print(" ");
  Serial.print(humid);
  Serial.println();
  
  String url = webserverIP + "/htu21?";
  url += "T=";
  url += String(temp);
  url += "&H=";
  url += String(humid);
  
  if(WiFi.status()== WL_CONNECTED){   //Check WiFi connection status

     WiFiClient client;

     HTTPClient http;    //Declare object of class HTTPClient
 
     http.begin(client, url);    //Specify request destination
     http.addHeader("Content-Type", "text/plain");  //Specify content-type header
 
     int httpCode = http.POST("Message from ESP32");   //Send the request
     String payload = http.getString();                //Get the response payload
 
     Serial.println(httpCode);   //Print HTTP return code
     Serial.println(payload);    //Print request response payload

     http.end();  //Close connection
 
   }else{
      Serial.println("Error in WiFi connection");   
   }
  
  Serial.println();
  Serial.println("closing connection. going to sleep...");
  // go to deepsleep for 1 minutes
  //system_deep_sleep_set_option(0);
  //system_deep_sleep(1 * 60 * 1000000);
  delay(1*60*1000);
}

<br>
<br>

*This site was last updated {{ site.time | date: "%B %d, %Y" }}.*

