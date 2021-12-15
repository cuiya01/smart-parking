# smart-parking
## Introduction
### background
Whenever you drive to a place and need to park, are you still worry about finding a parking space? Are you wasting too much time in searching for a parking space? With smart parking, we can quickly determine and find the vacant parking spots and find the right parking spot for ourselves.
In the parking lot under the shopping mall or office building, a parking space indicator will be installed on the parking space to indicate whether the space is parked or not, when it is found to be a red light it means that the space is already occupied by the vehicle, the light is green then it means that the space is empty, we can quickly identify the empty space by the light in front of the parking space, and quickly find the parking space in order for us to avoid wasting too much time in lifting the car.


https://user-images.githubusercontent.com/92298865/146174071-b85d327e-f593-4db6-9f8d-e9fff5a95171.mp4


Please enjoy the demo video of my demo project before the detailed introduction.

### Ultrasonic distance measurement
Ultrasonic sensors are sensors developed using the properties of ultrasonic waves. We use ultrasonic sensors will generally be used for distance measurement, compared to other distance measurement sensors have easy to use, high sensitivity and other characteristics. For ultrasonic sensors various characteristics, ultrasonic detection is widely used in industry, national defense, biomedicine and other aspects.

### The principle of ultrasonic distance measurement
#### hs-sr04
Using IO trigger ranging, giving a high level signal of at least 10us.
the module automatically sends 8 square waves of 40KHz and automatically detects whether there is a signal return.
If there is a signal return, a high level is output through IO, and the duration of the high level is the time of ultrasonic wave from transmitting to returning. Distance = (high level time * speed of sound (340m/s))/2;

![image](https://user-images.githubusercontent.com/92298865/145706433-3fcefb96-d004-4ef6-be78-4e4d0e16c134.png)


* The first digital pin is used to give the Trig pin of the ultrasonic module a high level signal of at least 10μs to trigger the distance measurement function of the SR04 module.
* 
![image](https://user-images.githubusercontent.com/92298865/145706460-7f0ebaad-c930-40be-89cd-321daa697700.png)

* After triggering, the module will automatically send 8 ultrasonic pulses of 40KHz and automatically detect if a signal is returned. This step will be done automatically by the module internally.
* 
![image](https://user-images.githubusercontent.com/92298865/145706463-2f514818-1853-4288-bd1d-31399d8f356d.png)

* If a signal is returned, the Echo pin will output a high level, and the duration of the high level is the time between the emission and the return of the ultrasonic wave. At this point, we can use the pulseIn() function to get the result of the distance measurement and calculate the actual distance from the object to be measured.
*The 
![image](https://user-images.githubusercontent.com/92298865/145706469-6a12ef0c-e9b7-4500-bfc6-f854dc085522.png)


### Ultrasonic sensor pin definition
Ultrasonic sensor pins Definition
vcc VCC
trig Transmitter
echo Receiver
gnd GND
### Hardware
arduino uno wifi master controller*1

ultrasonic sensor*2

buzzer*1

button*1

servo*1

red led*2

green led*2

10 kOhm resistor*1

100Ohm resistor*1

220hm resistor*4

### Software
arduino

mqtt

grafana
## Steps
Steps involved in this project.

1. Set up the Wi-Fi link
* Include the necessary libraries.
* Create a header file to store Wi-Fi credentials.
* Configure the publisher device to create three topics and publish them to a broker.
* Configure the subscriber device to subscribe to the three topics.
* Encryption
*publish 


2. link sensor
![circuit diagram_bb](https://user-images.githubusercontent.com/92298865/146112310-f0a5e115-2b77-44f1-82cf-5a03b6c431cb.jpg)


3. Storing data on a RPI gateway

* Installing Raspberry Pi imager
* Select sd card and setup some of the SSH / SSID info
* Insert the card into the RPi and power it up
* Log into the device using SSH



4. Visualising time series data

* Installing the Influx, Telegraf and Grafana
* Setting up Telegraf configuration Telegraf configuration
* My address http://stud-pi-ucfncui.local:3000
* Adding my first datasource-InfluxDB
* Create Dashboard and seeing the data


Block Diagram of Smart Parking System

![block diagram](https://user-images.githubusercontent.com/92298865/146174958-f8e203d5-1266-4475-8886-9c8c16de91a3.jpg)


Parking lot using ultrasonic sensor
Circuit diagram


Translated with www.DeepL.com/Translator (free version)
