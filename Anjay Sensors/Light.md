# Light Control Testing using Anjay Client 

-> We are going to build an light control by using Anjay LWM2M


# Procedure


-> Start the process by logging into the PI

        ssh dietpi@PI_IPADDRESS
        
 
## Installing c compiler

-> Check wethere the c compiler is installled or not by using the below command:

          gcc -v
          
          
          
          
          
          
          
          
          
          
          
 <img width="1440" alt="gcc" src="https://user-images.githubusercontent.com/112545596/192656151-230e4472-0d79-4183-b07f-e1faea988a00.png">









-> In case if c compiler is not installed then simply go to dietpi software and install.

            sudo dietpi-software
            install gcc
            
-> Install utils and libraries to build anjay

            sudo apt-get install git build-essential cmake libmbedtls-dev zlib1g-dev
            
            
            
## Build and install the avs_commons  
           
-> Now clone the avs_commons repository

             cd ~/projects
             git clone https://github.com/AVSystem/avs_commons
             
             
             
             
             
             
             
             
             
<img width="789" alt="clone avs" src="https://user-images.githubusercontent.com/112545596/192657525-2ede3a76-45d3-4d22-a1d6-b6d6a09bd348.png">








-> Installing avs libraries

          cd ~/projects/avs_commons
          cmake . && make && sudo make install
          
          
          
          
          
          
          
          
          
          
 <img width="983" alt="install avs" src="https://user-images.githubusercontent.com/112545596/192657690-e930ccf2-59e2-4504-baf4-8e753aecfd98.png">










<img width="1440" alt="install avs 1" src="https://user-images.githubusercontent.com/112545596/192657717-bfac7e97-14ea-43d7-b685-890eb0e21931.png">









## Anjay Libraries

-> retrieving the anjay code

           cd ~/projects
           git clone https://github.com/AVSystem/Anjay
           
           
           
           
           
           
           
           
           
 <img width="728" alt="retrive ajay code" src="https://user-images.githubusercontent.com/112545596/192658164-4ee59dfa-10a0-4d7d-bacc-1b139a4c79d1.png">









-> Building the anjay code

           cd ~/projects/Anjay
           git submodule update --init
           cmake . -DDTLS_BACKEND="mbedtls"
           make -j
           
           
           
           
<img width="1406" alt="build " src="https://user-images.githubusercontent.com/112545596/192660756-158a719b-f393-4299-95bd-94ff5a754f14.png">









<img width="1440" alt="installing anjay library" src="https://user-images.githubusercontent.com/112545596/192660830-b31c4dd0-83b6-488b-827c-3bea82f6b9bc.png">









* make -j




<img width="1440" alt="make -j" src="https://user-images.githubusercontent.com/112545596/192661082-0258f29d-617d-4f29-9b70-55aacb579c8a.png">









-> We will see our PI in the third party website. Now simply open the below link ehich will look like this

                https://leshan.eclipseprojects.io/#/clients
                
                
                
                
                
                
                
 <img width="1440" alt="leshan page" src="https://user-images.githubusercontent.com/112545596/192661438-3b16be61-1120-4f85-8de9-67de6215c6a4.png">









 -> Run the below command to see our PI

             ./output/bin/demo --endpoint-name $(hostname) --server-uri coap://leshan.eclipseprojects.io:5683
             
             
             
             
             
             
 * The one that is highlated is my PI.









<img width="1440" alt="output" src="https://user-images.githubusercontent.com/112545596/192661684-13005d51-ba30-443c-84cb-6a93f353f180.png">


 
 
 
 
 
 
 

               
## Build the ANJAY client

-> Now move to the anjay-esp32-client directory and setup the local enironment for using the esp tools

                cd ~/projects/Anjay-esp32-client
                . $HOME/esp/esp-idf/export.sh
                idf.py set-target esp32 












<img width="1440" alt="exportsh" src="https://user-images.githubusercontent.com/112545596/194372543-140ae3e5-c908-4838-95df-445656b897ef.png">











<img width="1106" alt="set-target" src="https://user-images.githubusercontent.com/112545596/194372670-75f9e9af-36b3-4d13-87ef-8b27fc834e71.png">












-> Setup the device requirements:
        
            cd ~/projects/Anjay-esp32-client
            idf.py menuconfig
            
            
            
            
            
            
<img width="1440" alt="setupdevicerequirements" src="https://user-images.githubusercontent.com/112545596/192842188-841e7098-9746-47fa-94e4-d1cfbe949e0a.png">











<img width="1440" alt="menuconfig" src="https://user-images.githubusercontent.com/112545596/192842657-a8cb8364-284f-429f-9dfe-e1dd35b1b24f.png">












-> navigate to "Component->" and select config/anjay-esp32-client:
        
       * navigate to Board options then we nedd to select the "light control enable" 
       
       Board options -> select " light control enable "










<img width="1440" alt="selecting light" src="https://user-images.githubusercontent.com/112545596/194375058-cad4a602-2c4e-41f9-ad4c-04d6204389a1.png">








       
-> Now go to light control options and we need to select light and select "Red light" and we need to enter the pin number that we had plugged to esp32.Here i had taken red light, you can choose any light blue or anything but while configuring you need to specify the colour.

          light control options -> light -> select "Enable red colour" 
          
          
          
          
          
          
          
          
          
          
          
<img width="1440" alt="red color light" src="https://user-images.githubusercontent.com/112545596/194376602-bfba3865-9583-48a4-965b-43edd53080c1.png">

        
        
        
        




        * light control options -> Red colour pin -> pin number
        
        
        






<img width="1440" alt="pin number of light" src="https://user-images.githubusercontent.com/112545596/194377295-1772d1a6-3afa-47d2-8d50-4973f8d196e1.png">










-> navigate to Client options

   * Change Server URI from coaps://try-anjay.avsystem.com:5684 to coaps://YOUR_LESHAN_SERVER_IP_ADDR:5684 I used coaps://192.168.8.224:5684 Your IP my be          different.
   * In my case i had taken my own dietpi server ip address.
   
              coad://192.168.8.198:5683 
              
   * And you may or may not change endpoint name. But i suggest you to change the name for better understanding
   * URI Choose socket (UDP) ---> 
   * Choose security mode (Non-secure connection) --->
   * make sure these are entered correct, if you entered them wrong then you will not get output.
   
   
   
   
   
   
   
   
   
<img width="1440" alt="esp32 details" src="https://user-images.githubusercontent.com/112545596/194379123-2a60fe21-da31-4959-a3d7-160b1c971346.png">









-> navigate to "WiFi" :

   * Here we need to enter the SSID and password of our router.
  
             WIFI -> SSID -> Password
  
  
  
  
  
  




<img width="1440" alt="my network details" src="https://user-images.githubusercontent.com/112545596/194379923-7d076ae7-5499-4847-8ecd-7c37c949ff4c.png">










-> Build the code for the device using

             cd ~/projects/Anjay-esp32-client
             idf.py build
             
             
             
             
             
             
             
             
             
             
<img width="1440" alt="idf build" src="https://user-images.githubusercontent.com/112545596/194380571-306c14d4-cf1c-4279-a4c6-d822513ff4b1.png">









-> Fnd the port to perform flashing.

        ls -l /dev/ttyUSB*
        
        
        
        
        
        
<img width="704" alt="port" src="https://user-images.githubusercontent.com/112545596/192845851-5cfe61a6-0c45-40bc-903f-41a8b41804df.png">










-> change the port number in this line to load the code 

        cd ~/projects/Anjay-esp32-client
        sudo chmod 666 /dev/ttyUSB0
        idf.py -p 0 flash
        
        
        
        
        
        
        
        
        
        
<img width="1440" alt="flashing" src="https://user-images.githubusercontent.com/112545596/194382152-90328d14-a206-47c6-8c82-19f9a814d583.png">









-> Now check leshan server for the registration of your esp32.

   * jas is name of my ESP32 which i had named it. 







<img width="1440" alt="esp32 registered" src="https://user-images.githubusercontent.com/112545596/194382580-c47a4400-d3eb-47b0-8917-30c17280c246.png">









-> And my ESP32 is connected to wifi network.









<img width="1440" alt="esp32 connected to network" src="https://user-images.githubusercontent.com/112545596/192846763-bb672c67-6d1f-4a26-aee4-d71d24df68c6.png">









## Circuit Diagram



-> You need male to male connecting wires
-> A 220k resistor
-> ESP32
-> a light (may be red, blue)





<img width="752" alt="circuit diagram of light" src="https://user-images.githubusercontent.com/112545596/194383094-7eee72ad-9cb7-4876-a875-08fd3f94aba5.png">

-> make connections by taking the above diagram as the reference.








-> This is my circiut diagram and my connections.








![connections](https://user-images.githubusercontent.com/112545596/194383690-34aa6f42-565b-41a5-8e99-ae568e937cca.jpg)











## Result

-> On clicking the jas(anjay client) we go to Devices and in the bottom left we see the light control click on it then the interface opens and it wiil be like this












<img width="1440" alt="light output interface" src="https://user-images.githubusercontent.com/112545596/194386722-186f5af3-f598-4ee1-a4b0-5855c4acb0c7.png">










-> To turn on the light by clicking "W" in on/off, here we need to specify the boolean value - true or false. And we can set the dimmer to any integer value and click "W" which appers green at buttom.








<img width="1440" alt="light on" src="https://user-images.githubusercontent.com/112545596/194411860-345f13bf-00a7-41c9-9dee-101ec2708004.png">



















<img width="1440" alt="entering value bool" src="https://user-images.githubusercontent.com/112545596/194412098-38a21577-1b4f-4422-adba-f34a4e71b380.png">

















![on](https://user-images.githubusercontent.com/112545596/194412715-6b8d963c-dae1-4a54-b942-8b49ae46b7fb.jpg)













-> To turn of the light then simply enter boolean value as false and then click on "W" it writes and light turn off's.










<img width="1440" alt="light off" src="https://user-images.githubusercontent.com/112545596/194413008-9e9f855d-7027-4c9e-9e16-ee7abcc974d3.png">















![off](https://user-images.githubusercontent.com/112545596/194413122-80a538e0-9bee-4454-b9fe-a4f8cccc8077.jpg)









-> Video:










https://user-images.githubusercontent.com/112545596/194413242-e33c20cb-cf51-40e0-8bc5-8e73eea0027f.mov
