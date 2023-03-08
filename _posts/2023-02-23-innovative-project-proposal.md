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
1. 感測方式:亮度，溫濕度，語音
2. 供電方式:家用電源
3. 聯網方式:WiFi或BT

**所需相關技術：**
1. 照度感測: ADC界面讀取光敏電阻(GL5516)
2. 睡眠品質監測：整夜睡眠多項生理功能檢查
3. 語音偵測：語音控制方案(Knowles SmartMic - IA611)
4. 智慧燈泡連接

### 系統方塊圖
![](https://github.com/tingwei1103/MCU-project/blob/main/images/01.jpg?raw=true)

---

## Design Methodology (設計方法)
* Top-Down Design  ：由上層應用分析再區分出下層個別功能及所需軟硬體設計
* Bottom-Up Design ：由底層軟硬體元件往上組合出上層所需應用功能

---


### 參考圖片
![](https://s314.siliconimg.com/kb/content_images/2017/04/26/1322452/1493205170_887.jpg)

### 參考影片
<iframe width="1280" height="720" src="https://www.youtube.com/embed/a6Gz3g7VxSw" title="Welcome to Podtime" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

### 參考資料
https://www.hksilicon.com/articles/1322452

https://www.ntuh.gov.tw/SLP/Fpage.action?muid=1452&fid=1261

https://www.mouser.tw/new/knowles/knowles-ia611-processor/


<br>
<br>

*This site was last updated {{ site.time | date: "%B %d, %Y" }}.*


