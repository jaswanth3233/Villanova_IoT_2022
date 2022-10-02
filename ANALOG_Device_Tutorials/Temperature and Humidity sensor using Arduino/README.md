# Testing temperature and Humidity Sensor by using Arduino Software

The process is same as wiringpi, but there are slight changes in the circuit diagram. We are going to use ESP32.

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



-> After downloading, unzip the folder and then install the Arduino IDE Application. After installation the result is shown in the below image.







![arduino-start](https://user-images.githubusercontent.com/112545596/193431190-fe8f0645-888f-47da-a229-cd237d291d8f.png)









-> In the Arduino, go to Files and then to Preferences. In the Preferences add the below given link in the Additional boards manager URL's and you can also change the location of .ino files to any directory of your choice.

            * Files -> Preferences -> Additional Boards Manager URL's -> Add the url  

            https://dl.espressif.com/dl/package_esp32_index.json
   
   
   
   
   
   
   
 
 ![boardmanager url](https://user-images.githubusercontent.com/112545596/193431466-b4d26417-c439-4561-b81a-06e5253df555.png)
 
 
 
 
 
 
 
 
 
 
 
-> Next, go to tools and then navigate to Board, and then navigate to Boards Manager, and then search for "ESP32 by Espressif Systems", and then install.

            * Tools -> Board -> Boards Manager -> Search " ESP32 by Espressif Systems " -> Install.







![espressif system- install](https://user-images.githubusercontent.com/112545596/193431592-c25fa4ac-6594-459b-b267-4f62dffdede4.png)









![espressif system- installed](https://user-images.githubusercontent.com/112545596/193431596-eb3da3db-6acb-4fa7-b694-2db88c3e8606.png)










-> Select the ESP32 by going to tools, and then to Board, and then to ESP32, and select the ESP32 Wrover module.

            * Tools -> Board -> ESP32 -> Select ESP32 Wrover Module.









![esp32-Wrover module](https://user-images.githubusercontent.com/112545596/193431853-21f35bcf-45fc-432c-b087-6be2f8621f60.png)









-> Connect the ESP32 to laptop using the USB cable.

-> After connection, select the port of the usb cable by clicking tools and then select the port, and then select the COM3 port.

            * Tools -> Port -> Select "COM3".








![port](https://user-images.githubusercontent.com/112545596/193432149-e584eec5-8e33-4457-a713-83bef86cef7f.png)









-> Now download the git repository / external library by using the below link :

           http://github.com/beegee-tokyo/DHTesp
           
 ## or
 
 -> Simply go to library Manager and search for DHT 
 
     * library manager -> Search " DHT " -> Install.
     
     
     
     
     
     
 
 
 
 ![external library](https://user-images.githubusercontent.com/112545596/193432330-8047af6c-c34d-4f77-ae71-8a2b064e0aba.png)











## Circuit Diagram or Connections



-> connect pin 1 (vcc) of the DHT11 based on the circuit diagram and also make a ground connection.

-> Connect the pin 2 (signal) to the port number 13 of the ESP32.

-> pin 4 is connected to the ground.




-> Reference:










![circuit-diagram](https://user-images.githubusercontent.com/112545596/193432451-7968a73b-3549-4d70-a294-bf7911cd9b80.png)









![circuit](https://user-images.githubusercontent.com/112545596/193436914-e0362d7d-1c2f-4e7c-995c-2115fbb4b457.jpg)










## Program


-> To view the code : [program](https://github.com/jaswanth3233/Villanova_IoT_2022/blob/main/ANALOG_Device_Tutorials/Temperature%20and%20Humidity%20sensor%20using%20Arduino/Program.md)











-> To compile or verify the code use the check mark or tick mark on the top left conner.









![compiling or verify](https://user-images.githubusercontent.com/112545596/193432611-01de20ac-0484-4b23-aa87-769c23bb41c6.png)









![compilation and verification complete](https://user-images.githubusercontent.com/112545596/193432616-7f53ecf8-436f-4242-a2b8-01e5945cb670.png)









-> Use the Arrow mark which is next to check mark to upload the content to ESP32









![upload](https://user-images.githubusercontent.com/112545596/193432659-cba653da-6a30-4e46-8ce4-5d2c8c44a564.png)









-> You will receive the message that uploading is completed. Click the "Serial Monitor" on the top right corner.










![serial monitor](https://user-images.githubusercontent.com/112545596/193433136-13b2716b-ec81-42f4-bb2a-71d502fe8393.jpg)








-> Here is the important step, change the baud rate to 115200.









![baud rate](https://user-images.githubusercontent.com/112545596/193433227-6660b2da-79a7-4ae4-b4ae-883d42e54f1f.png)










-> After setting all the things we will now see the Temperature and Humidity readings









![output-1](https://user-images.githubusercontent.com/112545596/193433246-2de32aee-b03d-40b9-b566-936142016fc6.png)












![output-2](https://user-images.githubusercontent.com/112545596/193433249-60d2556b-8d3a-4304-b2e1-d4590a9606de.png)










## Video :











https://user-images.githubusercontent.com/112545596/193445541-8f626d3b-711c-494e-993a-217dd2013b11.mp4
















# Reference

-> The Freenove Ultimate Starter Kit: [Guide](https://github.com/Freenove/Freenove_Starter_Kit/blob/master/Tutorial.pdf)





## Comparision 

-> According to the things that i went through in the DHT11 sensor with Raspberry PI and with Arduino IDE, I felt easy that using DHT11 sensor with the Arduino IDE is the easiest process. The main reason is its simplicity in doing it.
