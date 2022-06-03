# arduino491

https://youtu.be/AHDZInbjfrY

녹칸다의 ESPNOW시리즈이다!<BR>
이번편은 녹칸다가 새롭게 구입한 wemos D1 mini보드에서 espnow가 잘 작동되는지 확인해보도록한다!<BR>
그리고 아래와 같은 가정이 있다고 해보자!<BR>

A보드와 B보드가 있다!<BR>
A보드에는 센서값을 송신하고 B보드는 센서데이터를 수신한다!<BR>
A보드는 외부에 있어서 베터리가 달려있고 B보드는 집안 어딘가 상시전원을 공급받는다!<BR>
이때 A보드가 소모하는 전류량을 최소로하면서 B보드에게 일정한 간격으로 센서값을 전송할 수 있도록 예시를 구현한다!<BR>
A보드가 센서값을 전송하고 바로 deepsleep모드로 전환하는 것이다!<BR>

몇가지 센서를 준비해서 센서값이 잘 넘어가는지 확인해보자!<BR>
(온습도,이산화탄소,미세먼지,DS18B20,조도센서 등등)

그리고 B보드를 인터넷에 연결해서 MQTT로 데이터를 외부로 출력시켜보자!<BR>

(실제로한거)

1.Wemos d1 mini보드에서 espnow 양방향 통신이 잘 되는지 확인해보시오!(V3.0=76mA, CH340=90mA)

![491-1_bb](https://user-images.githubusercontent.com/106683637/171862399-b2d739a6-8aca-498d-8343-5220b8827e4e.jpg)
  
2.A보드가 B보드쪽으로 가상의 센서데이터를 전송하고 B가 MQTT로 스마트폰으로 데이터를 JSON으로 전송하도록 하시오!

3.A보드가 B보드로 ESPNOW로 10초에 한번 데이터를 전송한다고 할때 전송하고난 이외의 시간에 deepsleep을 걸어서 소모전류를 최소로 하시오!(저전력) -> (4.3ma)

![491-3_bb](https://user-images.githubusercontent.com/106683637/171862423-a9d3680b-4e31-4244-aea8-5c9abd5fefb9.jpg)
  
4.A보드에 온습도센서(DHT-11)를 연결해서 (3)예제의 방식으로 서버로 업로드하시오! ->(5.3ma)

![491-4_bb](https://user-images.githubusercontent.com/106683637/171862419-485ca44b-cb5d-4ad4-b035-a898220e9fad.jpg)
  
5.A보드에 이산화탄소센서(MH-Z19)를 연결해서 서버로 업로드하시오! -> (9.7ma)

![491-5_bb](https://user-images.githubusercontent.com/106683637/171862417-8a80769b-6d2d-46c7-8873-7ccdf564a022.jpg)
  
6.A보드에 미세먼지센서(PMS7003)를 연결해서 서버로 업로드하시오! -> (25~50ma)

![491-6_bb](https://user-images.githubusercontent.com/106683637/171862412-e48ac570-1698-4924-a83c-51a121ccb466.jpg)
  
7.조도센서(GY-30)를 연결해서 측정하시오!->(2.9ma)

![491-7_bb](https://user-images.githubusercontent.com/106683637/171862409-6b79a929-89a2-4241-8129-6fd33ee02356.jpg)
  
8.비접촉온도센서(MLX90614)연결해서 측정하시오 -> (4ma)
  
![491-8_bb](https://user-images.githubusercontent.com/106683637/171862406-5355dfe6-625b-4c28-ab9d-96169c3706cf.jpg)
  
  (Machine translation)

It is Nockanda's ESPNOW series!<BR>
In this episode, let's check whether espnow works well on the wemos D1 mini board that Nokkanda purchased newly!<BR>
And let's say we have the following assumptions:

There are A boards and B boards!<BR>
Board A sends sensor values ​​and board B receives sensor data!<BR>
Board A has a battery attached to it, and board B receives constant power somewhere in the house!<BR>
At this time, the example is implemented so that the sensor value can be transmitted to the B board at regular intervals while minimizing the amount of current consumed by the A board!<BR>
Board A transmits the sensor value and immediately switches to deepsleep mode!

Let's prepare a few sensors and check if the sensor value goes well!<BR>
(temperature and humidity, carbon dioxide, fine dust, DS18B20, illuminance sensor, etc.)

And let's connect B-board to the Internet and output data through MQTT!

(actually done)

1.Check if espnow bidirectional communication works well on Wemos d1 mini board! (V3.0=76mA, CH340=90mA)

2.Have board A transmit virtual sensor data to board B and have B transmit data as JSON to the smartphone using MQTT!

3.When board A transmits data once every 10 seconds by ESPNOW to board B, try deepsleep at the time other than transmission to minimize current consumption! (Low power) -> (4.3ma)

4.Connect the temperature and humidity sensor (DHT-11) to the A board and upload it to the server in the manner of (3) example! ->(5.3ma)

5.Connect the carbon dioxide sensor (MH-Z19) to the A board and upload it to the server! -> (9.7ma)

6.Connect the fine dust sensor (PMS7003) to the A board and upload it to the server! -> (25~50mA)

7.Connect the illuminance sensor (GY-30) and measure!->(2.9ma)

8.Connect and measure the non-contact temperature sensor (MLX90614) -> (4ma)
