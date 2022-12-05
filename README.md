# tel2022_DoItTomorrow 
> 2022東京威力科創機器人大賽  -- DIT__明天再做

> 創意技術獎 特優

## 賽程內容說明
* 上半場智慧賽道
  * 全程自動化
  * 辨識方塊，夾取至另一區堆疊
  * 通過顏色區域地板
  * 爬裝木條檻、檔版的斜坡


* 下半場鋼鐵擂台
  * 全程遙控
  * 夾取方塊
  * 操控者僅能觀看遠端畫面
  * 現場干擾源極多

## 開發軟韌體、框架
* 晶片：STM32H723ZG
* 開發平台：STM32CubeIDE、ROS
* 遙控：Bluetooth 5.0 x PS5手把
* 圖傳：小飛手模組 (含鏡頭)
* 影像辨識：OpenCV
* 通訊：ROS-STM --- rosserial_server
* 通訊：ROS_Arduino --- rosserial_python  

## 硬體層
* 底盤：麥克納姆倫 (Mecanum)、蹺蹺板
* 底盤驅動：直流馬達配 encoder、皮帶輪驅動
* 車體回授：車身周圍的微動裝置、BNO055 (IMU)
* 手臂：SCARA、末端三吸盤、氣動裝置 (電磁閥、氣泵)
* 鋼鐵擂台吸取方塊裝置：Intake
