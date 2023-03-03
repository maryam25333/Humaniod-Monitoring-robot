HUMANOID MONITORING ROBOT





## DESCRIPTION:
A humanoid monitoring robot that is designed to resemble humans in form, movement, performance and functions. Is equipped with cameras, servo motors, rechargeable batteries and other devices. These robots are typically used for surveillance, monitoring, and data collection purposes in areas where it may not be safe or feasible for humans to enter, such as hazardous environments or disaster zones. They can also be programmed to perform various tasks, such as detecting and tracking human activity, providing assistance in emergency situations, and even providing basic care in healthcare and elderly care settings. The development of humanoid monitoring robots is a rapidly evolving field, with advancements in technology continuously improving their capabilities and potential applications. 

## COMPONENTS:
	ESP32 cam 
	Pan Tilt Servo assembly
	SG90 servo motors
	L298N motor driver module
	7-12 V Rechargeable battery
	Ardunio uno
	Jumper wires

## CODE CONFIGURATION:
	Add ESP32 to Arduino IDE
To work with ESP32 variants, we need to add the boards into the IDE. To do this we do the following steps:
1.	Open the Arduino IDE
2.	Go to File | Preferences
	In the Additional Boards Manager URLs field, add the following 2 URLS separated with a comma:
	https://dl.espressif.com/dl/package_esp32_index.json,
	http://arduino.esp8266.com/stable/package_esp8266com_index.json

	Click OK
3.	Go to Tools | Board | Boards Manager
	In the Filter your search bar, enter ESP32
	Select esp32 by Espressif Systems and click Install
	Once installed, click Close
4.	Go to Tools | Board | ESP32 Arduino and select ESP32 Wrover Module

	Connect the Uno to the ESP32
Using jumpers or other temporary wiring, create the diagram as shown below to connect the ESP32CAM to the Arduino Uno for programming.
 



	Open Camera sample sketch
Once the ESP32 board is loaded into the IDE, now we can load the sample camera sketch to test the board.
1.	Begin by attaching the Arduino UNO to your computer
2.	In the IDE, go to File | Examples | ESP32 | Camera | Camera Web Server
3.	At the beginning where it says Select camera model
	Add a comment (double forward slash) in front of the line #define CAMERA_MODEL_WROVER_KIT
	Uncomment the line #define CAMERA_MODEL_AI_THINKER
	NOTE: The model may be different depending on where and when you purchase your version
4.	Add the SSID and Password for your WIFI
5.	On the Tools menu, make sure you have the following selected:
6.	Flash Mode: QIO
	Partition Scheme: Huge App (3MB…
	Flash Frequency: 40MHz
	Upload Speed: 115200
	Port: Arduino Uno
	Programmer: AVR ISP
	NOTE: This last last option wasn’t available for me and worked without a programmer set. I am leaving it here because it was in the initial instructions
 

	Upload sketch
Once the UNO and ESP32cam are connected and the sketch is ready, we can upload the code.
1.	In the Arduino IDE, click Upload
2.	Watch the black window at the bottom until it says Connecting
3.	On the ESP32cam, click the Reset button once and wait
4.	The upload will take about 1 minute
	NOTE: If this step fails for some reason, disconnect the USB cable from the UNO, reconnect it, and restart the Upload
5.	When the upload is finished, select Tools | Serial Monitor
6.	Ensure the speed is set to 115200
7.	On the ESP32cam disconnect the cable between GPIO 0 and GND and click the Reset button
8.	Watch the Serial Monitor for the IP address of the ESP32
	If you missed the IP address in the output, clicking the Reset button will restart the ESP32cam module and will reprint the address

	Connect to web page
Once you have the IP address from the Serial Monitor, enter it into a web browser. Note the web page may be slow to respond, especially when first accessed.
In the web browser, click Start Stream to view the camera.
To continue using the ESP32 cam, only power is needed to the 5V and GND pins.


## SOFTWARE FUNCTIONS:
 
  
This is a WI-FI controlled humanoid robot. It can be controlled using a mobile app. This mobile app can be open by entering an IP address (192.168.4.1) on the browser. Sometimes we might have to reconnect the WI-FI if app does not open. There are four buttons that handles the movement of the car left, right, backward and forward. Then there are buttons for the speed and light control. And we also have button PAN and TILT button. This PAN Button will handle the camera movement in left and right direction. However, TILT Button will handle the camera movement in upward and downward direction. The light button will be used to turn the flash light on and off. Moreover we can increase and decrease the intensity of this flash. The speed button can be used to control the speed of video streaming.




## HARDWARE CONFIGURATION:
We are going to make humanoid monitoring robot with pan tilt control. By using this pan tilt assembly we can rotate the camera horizontally and vertically. We can capture images by esp32 camera module and send these images to mobile application using Web socket through Wi-Fi connection. We can control robot by using own Web application. 
First assemble the pan tilt and fixed servos.  Then assemble the car now. First heat the wire with gear motors. Mount all four motors on car chassis using connecter and screws. Now attach the both car chassis plate using screws. Then we join the red to red and black to black wire on DC motors on each sides. Attach L298N motor module on car chassis and then we make connection. L298Nmotor
We connect right side motors to out one and out two pin to L298N motor module. Connect left side to out three and out four pin to motor driver module. Then we connect L298N motor to Esp32 cam. Connect both enA and enB pins to IO2 pin ESP camera. We will take +5 volt from L298N motor and provide to Esp32 camera module then fixed Esp32 camera module. Mount pan tilt assembly on car chassis connect pan servo and tilt servo to IO14 and IO15 respectively. Connect UBC to battery supply and provide +5 volt and ground to servos. Attach DC battery power connector to motor driver module. Then we attach wheels to car.
