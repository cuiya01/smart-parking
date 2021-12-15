# smart-parking
## Introduction
### background
* Whenever you drive to a place and need to park, are you still worry about finding a parking space? Are you wasting too much time in searching for a parking space? With smart parking, we can quickly determine and find the vacant parking spots and find the right parking spot for ourselves.
In the parking lot under the shopping mall or office building, a parking space indicator will be installed on the parking space to indicate whether the space is parked or not, when it is found to be a red light it means that the space is already occupied by the vehicle, the light is green then it means that the space is empty, we can quickly identify the empty space by the light in front of the parking space, and quickly find the parking space in order for us to avoid wasting too much time in lifting the car.

* core functionality

  1/click the button and the blocking pole up it make car come in

  2/determine the entries number into the parking lot based on the number of button presses

  3/when car parking in the space the led will changed from green to red.and the number of free slot will changed from 2 to 1 and shows in mqtt and grafana

  4/when the vehicle is too close the wall, it is easy to occur, so the buzzer is set to send an alarm

* Please enjoy the demo video of my demo project before the detailed introduction.



https://user-images.githubusercontent.com/92298865/146196352-a077c7b0-7ac3-4f75-8bde-bfe6cb75bd09.mp4




### Ultrasonic distance measurement
Ultrasonic sensors are sensors developed using the properties of ultrasonic waves. We use ultrasonic sensors will generally be used for distance measurement, compared to other distance measurement sensors have easy to use, high sensitivity and other characteristics. For ultrasonic sensors various characteristics, ultrasonic detection is widely used in industry, national defense, biomedicine and other aspects.

### The principle of ultrasonic distance measurement
#### hs-sr04
Using IO trigger ranging, giving a high level signal of at least 10us.
the module automatically sends 8 square waves of 40KHz and automatically detects whether there is a signal return.
If there is a signal return, a high level is output through IO, and the duration of the high level is the time of ultrasonic wave from transmitting to returning. Distance = (high level time * speed of sound (340m/s))/2;
![1](https://user-images.githubusercontent.com/92298865/146176513-24706af5-c962-4ad0-9425-46eb95173ce6.jpg)



* The first digital pin is used to give the Trig pin of the ultrasonic module a high level signal of at least 10μs to trigger the distance measurement function of the SR04 module.
* ![2](https://user-images.githubusercontent.com/92298865/146177723-1d9856e1-bdae-4f47-a279-781b52d7b512.jpg)

* After triggering, the module will automatically send 8 ultrasonic pulses of 40KHz and automatically detect if a signal is returned. This step will be done automatically by the module internally.
* ![3](https://user-images.githubusercontent.com/92298865/146177747-68c36cef-38fc-43bd-af2a-8d14be923c24.jpg)

* If a signal is returned, the Echo pin will output a high level, and the duration of the high level is the time between the emission and the return of the ultrasonic wave. At this point, we can use the pulseIn() function to get the result of the distance measurement and calculate the actual distance from the object to be measured.
* ![4](https://user-images.githubusercontent.com/92298865/146177773-e1312bd8-af4e-40fe-ada8-a83dc3cd2592.jpg)



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

1. Set up the Wi-Fi link and connect mqtt
* Include the necessary libraries.
* Create a header file to store Wi-Fi credentials.
* Configure the publisher device to create three topics and publish them to a broker.
* Configure the subscriber device to subscribe to the three topics.
* Encryption
*publish 

![image](https://user-images.githubusercontent.com/92298865/146184855-e605f2df-d481-41dc-8721-a9805c9b9b00.png)


2. link sensor
* circuit diagram

![circuit diagram_bb](https://user-images.githubusercontent.com/92298865/146112310-f0a5e115-2b77-44f1-82cf-5a03b6c431cb.jpg)
* phototype

![491639566582_ pic_hd](https://user-images.githubusercontent.com/92298865/146176185-5b07b744-ec83-4858-97b5-345c8252f4b8.jpg)
* get the data form arduino

![image](https://user-images.githubusercontent.com/92298865/146184918-2f237610-1798-4771-8bf2-b6be4139cbd4.png)


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
* data visualization：
  
  1/distance1
  
  The distance of the parking space can show whether there are cars in the place, so it can reflect whether people like the parking space, which can help to      plan   
  the location of the parking space better
  
  2/distance2
  
  3/freeslot
  
  It is possible to calculate the number of empty spaces in this parking lot to help people better plan whether to enter this parking lot to find a spot. 
  
  For managers, it is also possible to know how full this parking lot is.
  
  4/car count
  
  Helps managers understand how many vehicles enter the parking lot each day
  
![501639571585_ pic](https://user-images.githubusercontent.com/92298865/146187314-2ce818d6-617e-4ef6-a6eb-c5bee62b37a7.jpg)

* Block Diagram of Smart Parking System

![block diagram](https://user-images.githubusercontent.com/92298865/146174958-f8e203d5-1266-4475-8886-9c8c16de91a3.jpg)


Parking lot using ultrasonic sensor
Circuit diagram

