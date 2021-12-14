# smart-parking
## 简介
### background
在很多城市找到一个免费停车场非常困难，尤其是在一些节日。在这里，如果有人想带着私家车出门，他首先想到的是停车，他会把车停在哪里。大多数情况下，人们去一个停车场，发现所有的车位都满了，然后他不得不寻找另一个停车场。所以，这是一个很大的麻烦，很多人在他下车时一直担心他的车停在那里。

所以，我在想，如何解决这个问题，最后我成功地做了一个基于云的智能停车系统，我希望这个系统的实施可以解决我所在城市的停车问题。the things network对于此类工作来说确实是一个不错且合适的平台。

使用该系统，用户将能够从任何地方使用移动或网络应用程序轻松找到可用的停车场。系统每 30 秒更新一次停车数据。

在这个项目中，我将向您展示如何轻松构建这样的智能系统。当然，我会使用最酷的物联网云平台 the things network 平台。

在详细介绍之前，请欣赏我的演示项目的演示视频。


### 超声波测距
超声波传感器是利用超声波的特性研制而成的传感器。我们使用的超声波传感器一般会用来测距，相比其他测距传感器有着简单易用、灵敏度高等特点。对于超声波传感器各种特性，超声波检测广泛应用在工业、国防、生物医学等方面。

### 超声波测距的原理
#### hs-sr04
采用IO触发测距，给至少10us的高电平信号；
模块自动发送8个40KHz的方波，自动检测是否有信号返回；
有信号返回，通过IO输出一高电平，高电平持续的时间就是超声波从发射到返回的时间．距离=(高电平时间*声速(340m/s))/2;

![image](https://user-images.githubusercontent.com/92298865/145706433-3fcefb96-d004-4ef6-be78-4e4d0e16c134.png)


* 首先采用数字引脚给超声波模块的Trig引脚至少10μs的高电平信号，触发SR04模块测距功能；
* 
![image](https://user-images.githubusercontent.com/92298865/145706460-7f0ebaad-c930-40be-89cd-321daa697700.png)

* 触发后，模块会自动发送8个40KHz的超声波脉冲，并自动检测是否有信号返回。这步会由模块内部自动完成。
* 
![image](https://user-images.githubusercontent.com/92298865/145706463-2f514818-1853-4288-bd1d-31399d8f356d.png)

* 如有信号返回，Echo引脚会输出高电平，高电平持续的时间就是超声波从发射到返回的时间。此时，我们能使用pulseIn() 函数获取到测距的结果，并计算出距被测物的实际距离。
* 
![image](https://user-images.githubusercontent.com/92298865/145706469-6a12ef0c-e9b7-4500-bfc6-f854dc085522.png)


### 超声波传感器的引脚定义
超声波传感器引脚	定义
vcc	VCC
trig	发送端
echo	接收端
gnd	GND
### 硬件
arduino uno wifi  主控器*1

超声波传感器*2

buzzer*1

button*1

servo*1

red led*2

green led*2

10 kOhm resistor*1

100Ohm resistor*1

220hm resistor*4

### 软件
arduino

mqtt

## 步骤
本项目涉及的步骤：

1. 设置Wi-Fi链接
* Include the necessary libraries.
* Create a header file to store Wi-Fi credentials.
* Configure the publisher device to create three topics and publish them to a broker.
* Configure the subscriber device to subscribe to the three topics.
* 加密
*publish 

2. 设置时间

3. 链接传感器

4.Storing data on a RPI gateway

Installing Raspberry Pi imager
Select sd card and setup some of the SSH / SSID info
Insert the card into the RPi and power it up
Log into the device using SSH



5.Visualising time series data

Installing the Influx, Telegraf and Grafana
Setting up Telegraf configuration Telegraf configuration
My address http://stud-pi-ucfncui.local：3000
Adding my first datasource-InfluxDB
Create Dashboard and seeing the data


Block Diagram of Smart Parking System
![image](https://user-images.githubusercontent.com/92298865/146024837-c6d2d515-1cae-401b-a668-093745d41770.png)


Parking lot using ultrasonic sensor
电路图
