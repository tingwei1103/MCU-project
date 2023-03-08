---
layout: post
title: Innovative project proposal
author: [tingwei1103]
category: [Lecture]
tags: [jekyll, ai]
---

This homework is to specify a Future Home application and describe the key features, list all Design Considerations and the required technologies, then draw the System Block Diagram.

---
## Futre Home Applications


---


---
### Homework Report
**Contents:**<br>
* **應用與功能說明**
  - Specify the future home application, and Describe the key features
  - Describe the key features which may be applied to the home space (kitchen, living room, play room, study room, bed room)
* **設計考量與所需相關技術**
  - List all design considerations and the required technologies
* **系統方塊圖**
  - Draw a System Block Diagram


---


## 智慧睡眠倉
### 應用功能說明
1. 亮度偵測調節
2. 溫溼度偵測調節
3. 監測睡眠品質,並保存睡眠動態紀錄
4. 語音偵測與遙控
5. 鬧鐘喚醒功能

### 設計考量與相關技術
**系統設計考量：**<br>
1. 感測方式:亮度，溫濕度,語音
2. 供電方式:家用電源
3. 聯網方式:WiFi或BT

**所需相關技術：**
1. 照度感測: ADC界面讀取光敏電阻(GL5516)
2. 睡眠品質監測：藍牙穿戴式手環(ESP32+MPU6050), 運用三軸加速器偵測睡眠動態
3. 手勢偵測：MPU6050感測手勢動作之三軸加速器數值, 利用TinyML進行AI手勢辨識
4. 網路電台播放：ESP32 Internet Radio player
5. 智慧燈泡連接：AWS Alexa介接, 或藍牙命令操控燈光

### 系統方塊圖
![](https://github.com/rkuo2000/MCU-course/blob/main/images/Future_Home_morning_alarm_system.png?raw=true)

---

## Design Methodology (設計方法)
* Top-Down Design  ：由上層應用分析再區分出下層個別功能及所需軟硬體設計
* Bottom-Up Design ：由底層軟硬體元件往上組合出上層所需應用功能

---


### 參考影片
![](https://github.com/tingwei1103/MCU-project/blob/main/images/3DPW_Mega2560_RAMPS14_A4988_LCD.png?raw=true)
<iframe width="654" height="368" src="https://www.youtube.com/embed/moojunGu4UM" title="【DinTer】成為職業選手的必備條件？特哥不再玩台服的原因？得罪主席=陸服帳號被鎖十年...感謝粉絲熱情送帳號～瞬疾步伐葛雷夫Graves JG 頂級繞背！對面有怪獸啊！" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

<br>
<br>

*This site was last updated {{ site.time | date: "%B %d, %Y" }}.*


