# tel2022_DoItTomorrow 
> 2022東京威力科創機器人大賽  -- DIT__明天再做

> 創意技術獎 特優 $12000  OwOO

## 比賽內容概略
* 上半場智慧賽道
  * 全程自動化
  * 辨識方塊，夾取至另一區堆疊
  * 通過顏色區域地板
  * 爬裝木條檻、檔版的斜坡


* 下半場鋼鐵擂台
  * 全程遙控
  * 夾取方塊
  * 操控者僅能觀看遠端畫面
  * 現場訊號干擾嚴重

## 開發軟韌體、框架
* 晶片：STM32H723ZG
* 開發平台：STM32CubeIDE、ROS
* 遙控：PS5手把
* 圖傳：小飛手模組 (含鏡頭)
* 影像辨識：OpenCV
* 通訊：ROS-STM --- rosserial_server (CP2102 USB to TTL)
* 通訊：ROS-Arduino MEGA --- rosserial_python
* 通訊：PS5-Arduino MEGA --- Bluetooth 5.0

## 硬體
* 底盤：麥克納姆輪 (Mecanum)、皮帶輪驅動、蹺蹺板結構
* 驅動：底盤--直流馬達、SCARA--步進、Intake--堝桿馬達
* 車體回授：微動、encoder、BNO055 (IMU)
* 手臂：SCARA、末端三吸盤、氣動裝置 (電磁閥、氣泵)
* Intake：PU圓皮帶、捲線器
* 計算單元：Raspberry Pi 4B 
* 電源：2S*1、3S*1、行充*1

## Review 
1. RPi 4B, or saying that SBC boards, are NOT stable and reliable on commuication with stm32 by rosserial, especially working over 30 minutes or connecting to multiple devices.
2. rosserial_server, written in cpp, has higher quailty and error message display than rosserial_python. 
3. Bluetooth 5.0 is an AWFUL choice for remote control, having low adaptibilty to strong-interference environment, even merely 2~5m signal could be affected seriously.
4. Recognizing letters by OpenCV would NOT be reliable due to light interference. Machine learning (e.g YOLO) would be better alternative of OpenCV, be it the time cost of developing or the stability and accuracy of recognization outcomes.
5. Owing to time constraints, No integration of microswitch and IMU in this project. We calculate car pos and vel merely by receiving the datas of encoders.
