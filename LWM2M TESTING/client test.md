
# Client testing on Raspberry PI

I had used 2 different types of  client test on my PI
  
  ## * Speed Test
  ## * Iperf
  
  
 ## Speed Test
 
 -> First i checked whether my Raspberry pi is updated to latest version or by entering the following command PI gets updated to the latest version.
 
          sudo apt update
          
      
      
      
      
      
  <img width="1101" alt="update command speed test" src="https://user-images.githubusercontent.com/112545596/192201806-b4ce4159-cc3d-4322-9d1f-21ce01f4afb0.png">







-> After updating the PI, then by using the command i installed the speed test client into my PI.
  
          sudo apt install speedtest-cli
          
          
          
          
          
          
   <img width="1076" alt="installing speedtest" src="https://user-images.githubusercontent.com/112545596/192202331-64fc4c80-6d30-4107-bad2-5a7e8c4f0107.png">









-> Then we can test the speed of internet by entering the command, we can the download and the upload speed

            speedtest-cli
            
            
            
            
            
 
 
 
  <img width="897" alt="speedtest result" src="https://user-images.githubusercontent.com/112545596/192202559-63de9385-21da-42c9-9570-e086300f84f9.png">

   
   
   
   
   
   
   
   
 --> The Speedtest is completed.
  
  
  
  
  
  
  
  
  
  
  ## Iperf
  
  
  
  


-> Same as the speedtest we need to install the iperf by using the command:

            sudo apt-get install iperf
            
            
            
            
            
            
            
  <img width="1216" alt="installing iperf" src="https://user-images.githubusercontent.com/112545596/192205178-75399f4f-5e8a-4c5d-b9a7-519b571b8811.png">









-> Here we going to check whether there are connection to server by using this command:

          iperf -s
          
          
          
          
          
          
          
          
 <img width="1034" alt="server iperf" src="https://user-images.githubusercontent.com/112545596/192206698-94f219c4-0767-4c22-b78f-d715136b3b6b.png">









-> Now just exit by clicking control + C and the enter the command, u will be seeing the output








<img width="1440" alt="output iperf" src="https://user-images.githubusercontent.com/112545596/192207770-21d74ea8-5e03-42cf-96c2-01fe684073f6.png">





