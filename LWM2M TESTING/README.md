
# LWM2M Testing Using Raspberry PI 

Light Weight Machine to Machine is considered as a protocol used for the device management. The main objective of LWM2M is to progress a quick movable client-server designation to indulge machine to machine services.


## Steps

## login to Raspberry PI

-> command:
  
          ssh dietpi@IPADDRESS

 
 
## Install development environment on PI

-> In the terminal enter dietpi-software and dowmload the softwares by selecting the required software by entering the keyword Git and Java JDK and then      clicking spacebar and then go to install software then we will be seeing the list of softawres that we had selected and the then click ok to install.
   
   
        sudo dietpi-software
        
 -> For Git and Java JDk and checking versions
 
        - Git: Clone and manage Git repositories locally
          git --version
        
        - Java JDK: OpenJDK Development Kit
          java --version
          
          
          
          
          
          
 
 
 
 <img width="1440" alt="git install" src="https://user-images.githubusercontent.com/112545596/192336930-31eee909-f929-45e8-b15e-a2be7b4b19f3.png">

 
 
 
 
 
 
 
 
 
 
 
 
 
 
 <img width="1440" alt="java install" src="https://user-images.githubusercontent.com/112545596/192348679-10a7c44f-723e-4ef6-9451-02426f965bf8.png">













## Install Maven on the Raspberry Pi


-> Here we are going to create a directory called download and in the directory we are going to istall the apache maven and unpack the package.

        mkdir download
        cd download
        wget https://dlcdn.apache.org/maven/maven-3/3.8.6/binaries/apache-maven-3.8.6-bin.tar.gz
        unpacking : tar xzvf apache-maven-3.8.6-bin.tar.gz
 
-> Here we are going to check whether maven is insatlled or not by entering the command:

          mvn -v
          
          
-> Here we are going to add path for environment variable for java and the maven.

          echo 'PATH="${PATH}:~/download/apache-maven-3.8.6/bin"' >>  ~/.bashrc
          sudo echo 'JAVA_HOME="/usr/lib/jvm/java-17-openjdk-arm64"' >> ~/.bashrc
          
-> And to check the contents existed or not enter:
          
          nano ~/.bashrc
          
          
          
          
          
          
          
<img width="1440" alt="path" src="https://user-images.githubusercontent.com/112545596/192344496-548a6efb-cc0f-4105-81b2-c1131ff6cad9.png">









## Install Git and Build

-> clone the leshan repostory by following commands:

          cd
          mkdir projects
          cd projects
          git clone https://github.com/eclipse/leshan.git
          
          
          
          
          
          
          
          
          
 <img width="1440" alt="leshan install" src="https://user-images.githubusercontent.com/112545596/192345549-23425ea3-9a0d-45f5-9d6a-d592b1390d3e.png">










-> Build leshan by using the commands:

        cd ~/projects/leshan
        mvn clean install
        
        
        
        
        
        
        
        
 <img width="1440" alt="mvn clean 1" src="https://user-images.githubusercontent.com/112545596/192345982-46ab1b29-2e25-4a71-a128-b52f8901e8a2.png">














<img width="1440" alt="mvn clean 2" src="https://user-images.githubusercontent.com/112545596/192346064-7d0dc1da-a6dc-45d9-b2b7-4d821ee6f765.png">










* It took me 22 minutes for completion of this build.








## Test the Leshan Server

-> we start the process by executing the commands

        cd ~/projects/leshan
        java -jar leshan-server-demo/target/leshan-server-demo-*-SNAPSHOT-jar-with-dependencies.jar &
        
        
        
        
        
        
        
        
        
  <img width="1440" alt="launch leshan" src="https://user-images.githubusercontent.com/112545596/192347033-3f6d8eae-b5bc-4e99-a4cc-0b81902c081c.png">
  
  
  
  
  
  
  
  
  
  
-> No enter the url to Connect on Leshan demo UI

          http://RPI_IPADDR:8080
          
-> run the leshan client to add it to the page

         java -jar leshan-client-demo/target/leshan-client-demo-*-SNAPSHOT-jar-with-dependencies.jar
         
         
         
         
 -> Here in the leshan page we wii be seeing your Dietpi registered
 
 
 
 
 
 
 
 
 
 
 <img width="1440" alt="output leshan" src="https://user-images.githubusercontent.com/112545596/192348006-7171421e-03d4-4757-b6df-411e1b8e0345.png">









