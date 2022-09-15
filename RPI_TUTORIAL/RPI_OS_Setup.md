
# Setting up dietpi on a Raspberry PI via wifi

## Hardware

1. 32GB Sd-card class-10, i am using sandisk ultra 32gb class-10. 
2. Raspberry Pi 4 2Gb and adapter and c-type cable.
3. GL.iNet GL-MT300N-V2 portable mini travel wireless pocket router(Personal Network) and the network must be configured and ready to connect.
4. laptop - I am using MacBook Air M1-chip and memory of 16GB.

## Setup

1. We need a archiver extractor, so in my case i am using unarchiver. url: https://theunarchiver.com 
2. I downloaded the balenaEtcher to burn the data into the sd card. url: https://www.balena.io/etcher/
3. Download the Disc Image from the Diet Pi website 
4. So I am choosing to use: ARMv8 64-bit image from the Diet pi Website: https://dietpi.com/downloads/images/DietPi_RPi-ARMv8-Bullseye.7z  
5. later on unwrap the cocntents of the disc image and later on fetch that image from you local directory
6. Run the Balena Etcher application and upload the disc image you have downloaded 
7. next step would be to select the target memmory drive for the disc image flash burn 
8. Insert your SD card to the laptop and the etcher software will recognise the target location and after selecting your target memory and flash the disc image.



9. <img width="1440" alt="burning image into sd card" src="https://user-images.githubusercontent.com/112545596/190391687-a7b1f06a-9a0d-4708-a001-c177052806b9.png">



10. after completion please unplug the sd card from your laptop
11. later on view the files in the sd card and it will be required to configure the network settings
12. modify the settings in the dietpi.txt and dietpi-wifi.txt as follows:
13. In dietpi-wifi.txt:
       aWIFI_SSID[0]='jaswanth_iot'  
       aWIFI_KEY[0]='**********'
13. And in dietpi.txt:
       AUTO_SETUP_LOCALE=en_US.UTF-8
       AUTO_SETUP_KEYBOARD_LAYOUT=us
       AUTO_SETUP_TIMEZONE=America/New_York
       AUTO_SETUP_NET_ETHERNET_ENABLED=0
       AUTO_SETUP_NET_WIFI_ENABLED=1
       AUTO_SETUP_NET_WIFI_COUNTRY_CODE=US
       AUTO_SETUP_DHCP_TO_STATIC=1
       AUTO_SETUP_NET_HOSTNAME=DietPi_{YOUR_INITIALS}
       AUTO_SETUP_HEADLESS=1
       AUTO_SETUP_AUTOSTART_TARGET_INDEX=1
       SURVEY_OPTED_IN=0
       CONFIG_SERIAL_CONSOLE_ENABLE=1

14. And save the changes and eject the sd card.
15. I had inserted the sd card into the Rasberry Pi.
16. And after powering up the pi you will see the red led turn on and the green light will start to blink and Wait until the green light has stopped           blinking. It took me 6 minutes for the green light to stop blinking.
17. The next step would be logging into the Router Admin panel and check whether pi is connected to the network or not. If it's connected then you will see     the IP Address of the pi.



<img width="1440" alt="client_pi" src="https://user-images.githubusercontent.com/112545596/190393605-34ac59e9-9bec-4493-ba30-296c6096cf7d.png">



18.Now we go to the terminal and run the following commands :
        ssh root@IP ADDRESS OF PI
        password: dietpi(default)
   It bootsup the pi.
        
 
 
<img width="1440" alt="boot-up pi" src="https://user-images.githubusercontent.com/112545596/190394611-15fc89b2-857b-416a-b62b-33378e12db7b.png">



<img width="1440" alt="boot-up pi2" src="https://user-images.githubusercontent.com/112545596/190394707-90973a1c-1c37-4d1f-bc22-9096870008c3.png">



<img width="1440" alt="booy-up pi3" src="https://user-images.githubusercontent.com/112545596/190394830-51e339d4-badf-450e-af7a-a50692c46e28.png">



19. Now we re-enter the ssh and password which navigates to the blue terminal.
20. Here we will be changing the password of both dietpi-software and unix user



<img width="1440" alt="change password" src="https://user-images.githubusercontent.com/112545596/190396076-20170769-a740-4ecc-a0ef-f3850f5fe6aa.png">



<img width="1440" alt="change password 1" src="https://user-images.githubusercontent.com/112545596/190396178-4bc859e0-235c-4005-b83a-eac65dbdd0ec.png">



<img width="1440" alt="configuration" src="https://user-images.githubusercontent.com/112545596/190396480-ff2b6386-69cd-4082-9088-53d294129c34.png">
Here it just enabled protection for the pi and i clicked ok.




After all the setup steps we endup at main menu of the OS installation 
