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









-> Now connect the ESP32 to the laptop using the USB cable.

-> After connection, we need to select the port of the usb cable by clicking tools and then select the port and then select the COM3 port.

* Tools -> Port -> Select "COM3".








![port](https://user-images.githubusercontent.com/112545596/193432149-e584eec5-8e33-4457-a713-83bef86cef7f.png)









-> Now download the git repository / external library by using the below link :

           http://github.com/beegee-tokyo/DHTesp
           
 ## or
 
 -> Simply go to library Manager and search for DHT 
 
     * library manager -> Search " DHT " -> Install.
     
     
     
     
     
     
 
 
 
 ![external library](https://user-images.githubusercontent.com/112545596/193432330-8047af6c-c34d-4f77-ae71-8a2b064e0aba.png)











## Circuit Diagram or Connections



-> 

->

->

->



-> Reference:










![circuit-diagram](https://user-images.githubusercontent.com/112545596/193432451-7968a73b-3549-4d70-a294-bf7911cd9b80.png)









## Program


-> To view the code : [program](https://github.com/jaswanth3233/Villanova_IoT_2022/blob/main/ANALOG_Device_Tutorials/Temperature%20and%20Humidity%20sensor%20using%20Arduino/Program.md)











-> To compile or to verify the code use the check mark or tick mark on the top left conner.









![compiling or verify](https://user-images.githubusercontent.com/112545596/193432611-01de20ac-0484-4b23-aa87-769c23bb41c6.png)









![compilation and verification complete](https://user-images.githubusercontent.com/112545596/193432616-7f53ecf8-436f-4242-a2b8-01e5945cb670.png)









-> use the Arrow mark which is beside the check mark to upload the content to the ESP32









![upload](https://user-images.githubusercontent.com/112545596/193432659-cba653da-6a30-4e46-8ce4-5d2c8c44a564.png)









-> Now you will be receiving the message that uploading is completed and after that click the "Serial Monitor" on the top right conor










![serial monitor](https://user-images.githubusercontent.com/112545596/193433136-13b2716b-ec81-42f4-bb2a-71d502fe8393.jpg)








-> Here is the important step we need to change the baud rate to 115200.









![baud rate](https://user-images.githubusercontent.com/112545596/193433227-6660b2da-79a7-4ae4-b4ae-883d42e54f1f.png)










-> After setting all the things we will now see the Temperature and Humidity readings









![output-1](https://user-images.githubusercontent.com/112545596/193433246-2de32aee-b03d-40b9-b566-936142016fc6.png)












![output-2](https://user-images.githubusercontent.com/112545596/193433249-60d2556b-8d3a-4304-b2e1-d4590a9606de.png)









# Reference

-> The Freenove Ultimate Starter Kit: [Guide] (file:///C:/Users/sunka/Desktop/IOT/Freenove_Ultimate_Starter_Kit_for_ESP32-master/C/C_Tutorial.pdf)




