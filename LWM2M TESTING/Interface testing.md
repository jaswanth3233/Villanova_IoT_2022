
# Install Software to Build ESP32 code

-> We are going to build the Hello world program and the Blink project on ESP32

## Requirements

* A wifi router, laptop and Raspberry PI 
* Laptop to work a console 2 and ESP32



## Procedure

-> login to your Raspberry pi using

        ssh dietpi@PI_IPADDRESS
        
-> Now Clone Anjay-esp32-client repository to Raspberry PI

        cd projects
        git clone --recurse-submodules --remote-submodules https://github.com/pschragger/Anjay-esp32-client
        
        
        
        
        
 
 
 
<img width="1440" alt="git clone" src="https://user-images.githubusercontent.com/112545596/192446819-1cd4303c-3abe-492e-9feb-5e34e753bb41.png">








-> Install build tools for ESP-IDF

        ison gperf python3 python3-pip python3-setuptools cmake ninja-build ccache libffi-dev libssl-dev dfu-util libusb-1.0-0
        
        
        
        
        
        
        
        
<img width="592" alt="esp-idf install" src="https://user-images.githubusercontent.com/112545596/192447472-71b39de2-0e46-495d-bb5c-1df17063b7c0.png">








-> Now download the esp-idf repository by following commands:

         mkdir -p ~/esp
         cd ~/esp
         git clone -b v4.4 --recursive https://github.com/espressif/esp-idf.git










<img width="1440" alt="download esp-idf" src="https://user-images.githubusercontent.com/112545596/192447923-b0e62f08-480b-4c97-b69f-3a578970d859.png">










-> Install the esp-idf by following the commands

        cd ~/esp/esp-idf
        ./install.sh all
        
        
        
        
        
        
        
        
        
 <img width="1155" alt="install esp-idf" src="https://user-images.githubusercontent.com/112545596/192448428-960112de-b0d4-4081-b514-8e646392c650.png">
















<img width="1440" alt="installatuion esp" src="https://user-images.githubusercontent.com/112545596/192449917-c394114f-a2bf-4dc0-bc09-5e0cae2c85c8.png">













-> Setup environment variables

        . ~/esp/esp-idf/export.sh
        
        
        
        
        
        
        
        
        
        
 <img width="660" alt="environment setup idf" src="https://user-images.githubusercontent.com/112545596/192448811-1733186a-af26-41ae-a9a1-d79dd006672b.png">









-> Test with Hello-world project and then setup the directory. After setting up we need to connect the esp32 to the PI using the usb cable.

        cd ~/esp
        cp   -r $IDF_PATH/examples/get-started/hello_world .
        
        
        
        
        
        
        
        
        
 <img width="692" alt="setup project" src="https://user-images.githubusercontent.com/112545596/192450157-62b3fb47-b88b-4556-af48-f7c08bd3bdee.png">









-> Continue the process by entering commands:

          . ~/esp/esp-idf/export.sh
          cd $IDF_PATH/examples/get-started/hello_world 
          idf.py set-target esp32
          idf.py fullclean
          idf.py menuconfig







<img width="1196" alt="build project" src="https://user-images.githubusercontent.com/112545596/192450881-5cb6ac4b-7f7d-4d2e-b8af-ba53abce0935.png">









-> After entering the menuconfig command, it nagivates to the page then simply click Save [S] then quit [Q] the config menu will now build the hello-world    program









<img width="1440" alt="menuconfig" src="https://user-images.githubusercontent.com/112545596/192451849-e1d7e1eb-b8b4-41bf-915f-f290d2590f7d.png">









-> to build idf

     idf.py build
     
     
     
     
     
     
     
     
     
     
    
 <img width="1440" alt="idfpybuild" src="https://user-images.githubusercontent.com/112545596/192453048-cb95c22e-d211-40b2-955c-ba2eb24eac02.png">










-> Now we have to find the usb that the esp is connected to

       lsusb
       
       
       
       
       
       
       
       
 <img width="801" alt="lsusb" src="https://user-images.githubusercontent.com/112545596/192453524-6d445604-ac69-4c9c-a722-6d807f60de73.png">









-> I choose the CH340 serial converter

find the port number /dev/ttyUSB[PORTNUMBER]

      ls -l /dev/ttyUSB*
      sudo chmod 666 /dev/ttyUSB0
      idf.py -p 0 flash










<img width="1440" alt="ttyusb" src="https://user-images.githubusercontent.com/112545596/192458024-ba964039-1d59-4ea2-a198-ae67987f726c.png">











-> Wgen we run the below command we can see the output as an infinite loop.

        idf.py -p /dev/ttyUSB0 monitor
        
        
        
        
        
        
        
        
        
        
        
        
<img width="1440" alt="helloworld output" src="https://user-images.githubusercontent.com/112545596/192458441-1dbce537-5efd-444d-b8b4-dd5071c8800f.png">










-> To stop this process we open another terminal and login into PI agian and enter the below command :

       ps aux | grep monitor
       
       
       
       
       
       
       
       
       
       
  <img width="1440" alt="grep" src="https://user-images.githubusercontent.com/112545596/192459039-f7d3986f-aad3-4ff6-842e-415544eb66d6.png">




* We can kill the process.





# Blink Project

## Procedure

-> We need to create a new directory 

        . ~/esp/esp-idf/export.sh
        cd ~/esp
        cp   -r $IDF_PATH/examples/get-started/blink .
        
        
        
        
        
        
<img width="928" alt="new directory 1" src="https://user-images.githubusercontent.com/112545596/192460896-df0f53e6-abc8-4fce-882d-737e0b9196aa.png">









-> We need to build the blink project

        . ~/esp/esp-idf/export.sh
        cd $IDF_PATH/examples/get-started/blink
        
        
        
        
        
        
        
        
 <img width="845" alt="new directory" src="https://user-images.githubusercontent.com/112545596/192461370-334ba6c4-adec-4d0d-b439-f50b22bd0f94.png">







<img width="1440" alt="build blink" src="https://user-images.githubusercontent.com/112545596/192461494-3887b468-c133-4c6c-880e-95206e5a7850.png">






        idf.py set-target esp32
        idf.py fullclean
        idf.py menuconfig
 
 
 
 
 
 
 
 
 <img width="1440" alt="menuconfig" src="https://user-images.githubusercontent.com/112545596/192461664-7765280f-c801-49dd-8e7b-badc432d6f8c.png">


* Here just click save[S] and the Quit[Q] 








-> We are going to build the code and look into it

        cd $IDF_PATH/examples/get-started/blink idf.py build
        cd ~/esp/esp-idf/examples/get-started/blink/main
        nano blink_example_main.c









<img width="1440" alt="build code" src="https://user-images.githubusercontent.com/112545596/192462516-9e34ab8c-fa24-4efc-9833-c153dbc18275.png">









<img width="1440" alt="program" src="https://user-images.githubusercontent.com/112545596/192462589-0a3a0edc-a178-4ad8-a015-80e1c14955f5.png">









-> Here we are going to change the settings in menuconfig
        
        cd ~/esp/esp-idf/examples/get-started/blink
        idf.py menuconfig
        
-> Follow the below steps to change the configurations
        
        i. navigate to the "Example Configuration" and hit enter
        ii. there are two settings Blink GPIO number and Blink Perion in ms
        iii. change the blink period in ms to 5 seconds ( 5000 ) 
        iv. save the results to the sdkconfig (S then Q )
        
        
        
        
        
        
        
 
 
 <img width="1440" alt="blink 1000" src="https://user-images.githubusercontent.com/112545596/192463347-691e86c5-e63e-416c-a583-d4ca4fd192d2.png">











<img width="1440" alt="blink 5000" src="https://user-images.githubusercontent.com/112545596/192463431-cf163278-24de-46d6-aa14-3bfa1103b4c0.png">









-> After this you need to flash into esp32, which is same as the hello world


-> And this the output












https://user-images.githubusercontent.com/112545596/192651264-7d574e47-5d18-4b46-acef-362639ca0067.mov



