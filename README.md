### Introduction
ESP-32 CAM을 활용한 [JOOTOPIA 프로젝트](https://github.com/nerdroid-labs/jootopia-server)의 카메라 아두이노 소스입니다.
 

### Configuration
소스를 ESP-32 CAM에 업로드하기 전에, WIFI 연결 정보와 카메라에게 배정할 IP 주소를 입력합니다.
```
    30	//Replace with your network credentials
    31	const char* ssid = "";
    32	const char* password = "";
    33
    34	//Replace with your camera address
    35	IPAddress ip (192, 168, 0, 0);
    36	IPAddress gateway (192, 168, 0, 0);
    37	IPAddress subnet (255, 255, 255, 0);
```

### Arduino IDE Upload Setting
+ Board: ESP32 Arduino → ESP32 Wrover Module
+ Upload Configuration
    + Upload Speed: 115200
    + Flash Frequency: 40MHz
    + Flash Mode: QIO
    + Partition Scheme: Huge APP (3MB No OTA)
    + Core Debug Level: None

### Reference
https://randomnerdtutorials.com/esp32-cam-video-streaming-web-server-camera-home-assistant/
