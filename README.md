### Introduction
ESP-32 CAM을 활용한 [JOOTOPIA 프로젝트](https://github.com/nerdroid-labs/jootopia-server)의 카메라 아두이노 소스입니다.
 

### Configuration
소스를 ESP-32 CAM에 업로드하기 전에, WIFI 연결 정보와 카메라에게 배정할 IP 주소를 입력합니다.
```
    jootopia-cam.ino
    
    30	//Replace with your network credentials
    31	const char* ssid = "";
    32	const char* password = "";
    33
    34	//Replace with your camera address
    35	IPAddress ip (192, 168, 0, 0);
    36	IPAddress gateway (192, 168, 0, 0);
    37	IPAddress subnet (255, 255, 255, 0);
```

카메라 렌즈마다 상하좌우가 다른 경우가 있는데, 아래와 같이 set_hmirror와 set_vflip으로 해결할 수 있습니다.
```
    jootopia-cam.ino
    
   265	  // Camera init
   266	  esp_err_t err = esp_camera_init(&config);
   267	  sensor_t * s = esp_camera_sensor_get();
   268	  //  s->set_hmirror(s, 1); // 0 = disable , 1 = enable
   269	  //  s->set_vflip(s, 1); // 0 = disable , 1 = enable;
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
