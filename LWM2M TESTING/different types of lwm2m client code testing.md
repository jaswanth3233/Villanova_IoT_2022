# Building an LWM2M clients on RPI for ESP32

-> We are going to build an LWM2M Device using idf and the ANJAY Libraries


# Procedure


-> We are going to start the process by login in to the PI

        ssh dietpi@PI_IPADDRESS
        
 
## Installing c compiler

-> Here i am checking wethere the c compiler is installled or not by using this command:

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









-> Now we will be seeing our PI in the third party website. Now simply open the below link and it will like this

                https://leshan.eclipseprojects.io/#/clients
                
                
                
                
                
                
                
 <img width="1440" alt="leshan page" src="https://user-images.githubusercontent.com/112545596/192661438-3b16be61-1120-4f85-8de9-67de6215c6a4.png">









-> now run this command we will be sseing our PI

             ./output/bin/demo --endpoint-name $(hostname) --server-uri coap://leshan.eclipseprojects.io:5683
             
             
             
             
             
             
 * The one that is highlated is my PI.









<img width="1440" alt="output" src="https://user-images.githubusercontent.com/112545596/192661684-13005d51-ba30-443c-84cb-6a93f353f180.png">

               
