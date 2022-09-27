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









