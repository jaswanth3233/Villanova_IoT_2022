# Testing Temperature/Humidity Sensor on My RPI

  Here we are going to test the DHT11 sensor with PI. The DHT11 sensor which records the temperature and humidity.

## Required Equipment

1) Breadboard

2) Jump Wires

3) DHT11 temperature-Humidity sensor

4) Raspberry Pi

5) 10K ohm resistor


# Sprecifications of the Hardware Used



## DHT11 temperature-Humidity sensor







<img width="372" alt="dht11" src="https://user-images.githubusercontent.com/112545596/193397756-800d6bae-b8c0-4c8d-a31b-b494e4885a55.png">








![DHT11–Temperature-Sensor-Pinout](https://user-images.githubusercontent.com/112545596/193397973-9c53d99c-8220-4791-a9f7-1cfddb0aaccf.jpeg)





-> The ports in DHT11 
        1. vcc(+)
        2. Signal or data
        3. Not used 
        4. Ground
-> Supply Voltage: 3.5 to 5.5V

-> Output Signal: digital signal via single-bus

-> Operating Range and Accuracy (Humidity): 20-80% RH; +/-5% RH

-> Operating Range and Accuracy (Temperature): 0 to 50 C; +/-2% C

-> Average Sending Period: 2 seconds

-> Dimensions (excluding pins): 12.6mm (0.5") length x 5.83mm (0.23") width x 16mm (0.63") height

## Raspberry Pi 4 B+ 












![pi](https://user-images.githubusercontent.com/112545596/193397984-bbc9e716-caf6-4244-bbec-ebfff7f524ed.jpeg)






-> key features include a high-performance 64-bit quad-core
processor, dual-display support at resolutions up to 4K via a pair of
micro-HDMI ports, hardware video decode at up to 4Kp60, up to 4GB of RAM,
dual-band 2.4/5.0 GHz wireless LAN, Bluetooth 5.0, Gigabit Ethernet, USB 3.0,
and PoE capability (via a separate PoE HAT add-on).

Reference : https://static.raspberrypi.org/files/product-briefs/Raspberry-Pi-4-Product-Brief.pdf






## Bread Board 









![breadboad](https://user-images.githubusercontent.com/112545596/193398284-adca8cae-1e0f-4ad4-8be3-2e9a0d3b98c8.jpeg)








-> Distribution Strips are two

-> Wire Size is 21 to 26 AWG wire

-> Tie Points are two hundred

-> Withstanding Voltage is 1,000V AC

-> Tie points within IC are 630

-> Insulation Resistance is DC500V or 500MΩ

-> Dimension is 6.5*4.4*0.3 inch

-> Rating is 5Amps

-> ABS plastic through color legend

->ABS heat Distortion Temperature is 183° F (84° C)Hole or Pitch Style is 2.54mm







## wires and 10k ohm resisitor








![resistor](https://user-images.githubusercontent.com/112545596/193399060-ae309786-d40e-4b21-9dd0-3829c75b1578.jpeg)

-> The resistor that i used for this experinment is 10k ohm resistor and the resistor varies based on the ohm's like 1k ohm, 5k ohm's etc..











![wire](https://user-images.githubusercontent.com/112545596/193399215-765b827c-b0b8-4ced-8898-ac901b219b67.png)



-> In the connecting wires there are male to male, male to female and female to female.






# Circuit diagram of microcontroller to analog device


-> I am using 4-pin DHT11 sensor connect the circuit as shown in the below circuit diagram.


<img width="1319" alt="diagram" src="https://user-images.githubusercontent.com/112545596/193399328-df36b068-0871-441b-ab31-90ab5d7ddfd5.png">




-> DHT11 Sensor Vcc+ to Raspberry Pi 5V.
-> DHT11 Sensor GND to Raspberry Pi GND.
-> DHT11 Sensor Signal to Raspberry Pi PIN 7 (GPIO PIN 4).
-> Place 10K Ohm Resistor between DHT11 PIN 1 and PIN 2.


-> This is my circuit diagram after all connections.








![circuit diagram](https://user-images.githubusercontent.com/112545596/193400124-109e1c08-9c90-4b4f-9a3b-164a07b1af3c.jpg)













![setup](https://user-images.githubusercontent.com/112545596/193400179-b4a4e082-b488-4d44-aa99-f0c682ababee.jpg)







                         

# Installing wiringPi



-> Now we are downloading the WiringPi which is in GIT, to get it we need to install GIT by using this command:

      sudo apt-get install git-core
      
      







<img width="1440" alt="git core" src="https://user-images.githubusercontent.com/112545596/193400484-dda48c33-c49d-4dba-a2f9-b236b22c9e32.png">









-> Update PI using these commands:

        sudo apt-get update
        sudo apt-get upgrade
        
        
 -> The GIT link that i used is https://github.com/WiringPi/WiringPi
 
 -> Now use the above link to clone the repository into your PI
 
            git clone https://github.com/WiringPi/WiringPi
            
            
            
            
   
   
   
   
   
 <img width="1440" alt="gitcloning " src="https://user-images.githubusercontent.com/112545596/193400868-8cc4f232-9547-48f8-ac8c-a25161fbf3a0.png">









<img width="1440" alt="wirepi install" src="https://user-images.githubusercontent.com/112545596/193401042-ef5d541e-0f1f-4d2e-84e5-8e3e9153c699.png">

-> Here i just installed the WiringPi in my DietPi using sudo DietPi software











<img width="562" alt="wiring pi" src="https://user-images.githubusercontent.com/112545596/193401109-34807242-4580-474d-9d1d-b222cf67745b.png">














-> After cloning the repository, we are going to write the code by using nano command and save it in the wiringpi directory

        cd WiringPi
        
-> Now we nned to write the code for temperature and humidity using the nano command. Here an empty text area appears where you need to enter the code. 

        nano temp.c // Here temp is the program name.
        
-> The Program : 











<img width="1440" alt="program" src="https://user-images.githubusercontent.com/112545596/193401459-c82e688a-72dd-478c-9288-42f821e42924.png">














-> In the program you need to change the counter from 16 to 50. 

        if(counter > 16) to if (counter > 50)
        
-> Now execute the program by running the following commands:

        for compliation : gcc -o example example.c -lwiringPi -lwiringPiDev // Here the example is the program name. You can enter your program name.
        
        My program compliation step : [dietpi@DietPi:~/WiringPi$ gcc -o temp temp.c
        
        for execution or running :  sudo ./example
        
        My program execution step : sudo ./temp
        
        
 -> Output:     
        
        
        
 
 
 
 
 
 
 
 
 
 
 
 <img width="925" alt="output" src="https://user-images.githubusercontent.com/112545596/193402131-8837b081-dcd6-4740-89ce-7b0c0e1b7104.png">





