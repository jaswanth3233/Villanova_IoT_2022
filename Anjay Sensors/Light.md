# Building an LWM2M clients on RPI for ESP32

-> We are going to build an LWM2M Device using idf and the ANJAY Libraries


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









-> Run the below command to see our PI and i am doing this process in my Dietpi server.

 * we start the process by executing the commands

        cd ~/projects/leshan
        java -jar leshan-server-demo/target/leshan-server-demo-*-SNAPSHOT-jar-with-dependencies.jar &

 * Now enter the url to Connect to Leshan demo UI

          http://RPI_IPADDR:8080
          
 * Run the leshan client to add it to the page

         java -jar leshan-client-demo/target/leshan-client-demo-*-SNAPSHOT-jar-with-dependencies.jar 
         
         
         
 
 
 
 
 
 
 * In the leshan page we wii be seeing your Dietpi registered
 
 
 
 
 
 
 
 
 
 
 <img width="1440" alt="output leshan" src="https://user-images.githubusercontent.com/112545596/192348006-7171421e-03d4-4757-b6df-411e1b8e0345.png">
 
 
 
 
 
 
 
 

               
## Build the ANJAY client

-> Now move to the anjay-esp32-client directory and setup the local enironment for using the esp tools

                cd ~/projects/Anjay-esp32-client
                . $HOME/esp/esp-idf/export.sh
                idf.py set-target esp32 










<img width="1207" alt="local environment" src="https://user-images.githubusercontent.com/112545596/192841448-400c4c87-1c51-413b-ad30-7e5daf362698.png">












<img width="1166" alt="idfpysettarget" src="https://user-images.githubusercontent.com/112545596/192841751-3199d203-a2f7-4882-b6ab-0ef1f62cb868.png">











-> Setup the device requirements:
        
            cd ~/projects/Anjay-esp32-client
            idf.py menuconfig
            
            
            
            
            
            
<img width="1440" alt="setupdevicerequirements" src="https://user-images.githubusercontent.com/112545596/192842188-841e7098-9746-47fa-94e4-d1cfbe949e0a.png">











<img width="1440" alt="menuconfig" src="https://user-images.githubusercontent.com/112545596/192842657-a8cb8364-284f-429f-9dfe-e1dd35b1b24f.png">












* navigate to "Component->" and select config/anjay-esp32-client:
        
        Setup your config to be: (anjay-esp32-client) Endpoint name (coap://{LESHAN_SERVER_IP}:5683) Server URI Choose socket (UDP) ---> Choose security mode (Non-secure connection) --->

        navigate to "Board - > "

        navigate to "Client options ->"








<img width="1440" alt="client options" src="https://user-images.githubusercontent.com/112545596/192843523-57a3e78c-f638-439e-846b-a03586af4664.png">











        Change Server URI from coaps://try-anjay.avsystem.com:5684 to coaps://YOUR_LESHAN_SERVER_IP_ADDR:5684 I used coaps://192.168.8.224:5684 Your IP my         be different
        
        
        
        
        
        
        
        
        
        
        
        
<img width="1213" alt="change url" src="https://user-images.githubusercontent.com/112545596/192844457-8f234a45-7f03-46ce-af80-c5db58f17b6f.png">









* navigate to "WiFi ->" To enter your IOT ROUTER WIFI SSID and key to allow the esp32 acccess to your router and PI.









<img width="1440" alt="wifi" src="https://user-images.githubusercontent.com/112545596/192844811-2e13a5f0-61af-48c8-b6fe-97e581764735.png">





