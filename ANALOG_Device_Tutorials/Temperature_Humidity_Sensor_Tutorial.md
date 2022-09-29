# Testing Temperature/Humidity Sensor on My RPI

## Required Equipment

1) Breadboard

2) Jump Wires

3) DHT11 temperature-Humidity sensor

4) Raspberry Pi

5) 10K ohm resistor


# Sprecifications of the Hardware Used



## DHT11 temperature-Humidity sensor

Image 

Supply Voltage: 3.5 to 5.5V
Output Signal: digital signal via single-bus
Operating Range and Accuracy (Humidity): 20-80% RH; +/-5% RH
Operating Range and Accuracy (Temperature): 0 to 50 C; +/-2% C
Average Sending Period: 2 seconds
Dimensions (excluding pins): 12.6mm (0.5") length x 5.83mm (0.23") width x 16mm (0.63") height

## Raspberry Pi 4 B+ 


image 

Broadcom BCM2711, Quad core Cortex-A72 (ARM v8) 64-bit SoC @ 1.5GHz
1GB, 2GB, 4GB or 8GB LPDDR4-3200 SDRAM (depending on model)
2.4 GHz and 5.0 GHz IEEE 802.11ac wireless, Bluetooth 5.0, BLE
Gigabit Ethernet
2 USB 3.0 ports; 2 USB 2.0 ports.
Raspberry Pi standard 40 pin GPIO header (fully backwards compatible with previous boards)
2 × micro-HDMI ports (up to 4kp60 supported)
2-lane MIPI DSI display port
2-lane MIPI CSI camera port
4-pole stereo audio and composite video port
H.265 (4kp60 decode), H264 (1080p60 decode, 1080p30 encode)
OpenGL ES 3.1, Vulkan 1.0
Micro-SD card slot for loading operating system and data storage
5V DC via USB-C connector (minimum 3A*)
5V DC via GPIO header (minimum 3A*)
Power over Ethernet (PoE) enabled (requires separate PoE HAT)
Operating temperature: 0 – 50 degrees C ambient
* A good quality 2.5A power supply can be used if downstream USB peripherals consume less than 500mA in total.


## Bread Board 



image 

It's 2.2" x 7" (5.5 cm x 17 cm) with a standard double-strip in the middle and two power rails on both sides. 
You can pull the power rails off easily to make the breadboard as thin as 1.4" (3.5cm). 
You can also "snap" these breadboards together either way to make longer and/or wider breadboards.


## wires and 10k resisitor 

image iamge 


# Circuit diagram of microcontroller to analog device

image 


Connection Information : VCC to Pin 1 ( Pin of the DHT11 )
                         GND to Pin 4
                         GPIO PIN to Pin 2 
                         Pin 3 of the Sensor is always Idle 
                         

# Installing wiringPi




