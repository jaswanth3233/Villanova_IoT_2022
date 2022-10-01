# Testing temperature and Humidity Sensor by using Arduino Software

The process is same as the wiringpi, but there will be slight changes in the circuit diagram and we re going to use the ESP32.

## Hardware Requirements

* DHT11 Sensor 
* Breadboard
* ESP32-WROVER
* 4 jumper cables ( Male to Male)
* Resistor 10k ohm's



# Steps


## Software Requirements

-> Download the Arduino IDE from the website :

            https://www.arduino.cc/en/software



-> After downloading, unzip the folder and then install the Arduino IDE Application.After installation the result will be 







![arduino-start](https://user-images.githubusercontent.com/112545596/193431190-fe8f0645-888f-47da-a229-cd237d291d8f.png)









-> In the Arduino go to Files and then from files to Preferences. And in the Preferences add the below given link in the Additional boards manager URL's and also u can     change the location of the .ino files in your own directory.

* Files -> Preferences -> Additional Boards Manager URL's -> Add the url  

            https://dl.espressif.com/dl/package_esp32_index.json
   
   
   
   
   
   
   
 
 ![boardmanager url](https://user-images.githubusercontent.com/112545596/193431466-b4d26417-c439-4561-b81a-06e5253df555.png)
 
 
 
 
 
 
 
 
 
 
 
-> Now go to tools and then navigate to Board and then navigate to Boards Manager and then search for "ESP32 by Espressif Systems" and then install.

* Tools -> Board -> Boards Manager -> Search " ESP32 by Espressif Systems " -> Install.







![espressif system- install](https://user-images.githubusercontent.com/112545596/193431592-c25fa4ac-6594-459b-b267-4f62dffdede4.png)









![espressif system- installed](https://user-images.githubusercontent.com/112545596/193431596-eb3da3db-6acb-4fa7-b694-2db88c3e8606.png)










-> We need to select the ESP32 by going to tools from then go to Board and then ESP32 and select the ESP32 Wrover module.

* Tools -> Board -> ESP32 -> Select ESP32 Wrover Module.









![esp32-Wrover module](https://user-images.githubusercontent.com/112545596/193431853-21f35bcf-45fc-432c-b087-6be2f8621f60.png)









