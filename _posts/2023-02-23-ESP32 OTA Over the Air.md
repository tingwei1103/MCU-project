---
layout: post
title: ESP32 OTA (Over the Air)
author: [Richard Kuo]
category: [Lecture]
tags: [jekyll, ai]
---

.

---
## ESP32 OTA (Over the Air)


### 應用功能說明
1. 上傳檔案

### 系統方塊圖
![](https://github.com/tingwei1103/MCU-project/blob/main/images/ota.png?raw=true)



### 圖片
![](https://github.com/tingwei1103/MCU-project/blob/main/images/Screenshot_20230504-204948_Chrome.jpg?raw=true)

![](https://github.com/tingwei1103/MCU-project/blob/main/images/Screenshot_20230504-205031_Chrome.jpg?raw=true)




### 程式碼
#include <Arduino.h>
#include <WiFi.h>
#include <AsyncTCP.h>
#include <ESPAsyncWebServer.h>
#include <AsyncElegantOTA.h>

const char* ssid = "Free WiFi";
const char* password = "0901086625";

AsyncWebServer server(80);

void setup(void) {
  Serial.begin(115200);
  WiFi.mode(WIFI_STA);
  WiFi.begin(ssid, password);
  Serial.println("");

  // Wait for connection
  while (WiFi.status() != WL_CONNECTED) {
    delay(500);
    Serial.print(".");
  }
  Serial.println("");
  Serial.print("Connected to ");
  Serial.println(ssid);
  Serial.print("IP address: ");
  Serial.println(WiFi.localIP());

  server.on("/", HTTP_GET, [](AsyncWebServerRequest *request) {
    request->send(200, "text/plain", "Hi! I am ESP32.");
  });

  AsyncElegantOTA.begin(&server);    // Start ElegantOTA
  server.begin();
  Serial.println("HTTP server started");
}

void loop(void) {
}  


<br>
<br>

*This site was last updated {{ site.time | date: "%B %d, %Y" }}.*

