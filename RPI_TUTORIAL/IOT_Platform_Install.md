
# Setting up IoT software to run on PI

## Note 
   
   Make sure the Raspberry Pi and the laptop are connected to your router.
 
 
## Procedure

  1. SSH to the RPI using dietpi user
        
            -> ssh dietpi@[PI_IPADDRESS]
            -> Password: *******
     And after entering, it navigates you to Dietpi Software page.
     
     
     
     
     <img width="1440" alt="final " src="https://user-images.githubusercontent.com/112545596/190473283-a4c35641-9c94-44bb-a43c-c5e983710a13.png">






  2.Install software on the PI 
  
  -> Now search for softwares in Search Software section       
    i.search for mqtt and select 123 MQTT message broker install by hitting the spacebar you will see the '*' that means the software is selected and select ok.
    
    
    
    
    
    
    
   <img width="1440" alt="mqtt" src="https://user-images.githubusercontent.com/112545596/190474643-d6f1978e-6913-4695-b51c-ff4e3872850f.png">








   ii.search for node-red and select "122 Node-RED: tool for wiring devices, APIs and online services" install by hitting the spacebar you will see the '*' that means the software  and select ok.
   
   
   
   
   
   
   
   
   
   <img width="1440" alt="node-red" src="https://user-images.githubusercontent.com/112545596/190475084-77e80cd6-1497-4877-9bd5-2b85577bcfcf.png">







   iii.search for postgress and select "194 PostgreSQL: Persistent advanced object-relational database server" install by hitting the spacebar you will see the '*' that means the software  and select ok.
   
   
   
   
   
   
   
   
   
<img width="1440" alt="postgresql" src="https://user-images.githubusercontent.com/112545596/190477161-fb6c54b7-40f2-4bbc-a580-5a49d2676ec9.png">









3. Now we need to install the software by choosing the install option at the bottom of the menu.






<img width="1440" alt="install" src="https://user-images.githubusercontent.com/112545596/190476048-873ae623-4387-4d44-9768-c4ab6a3d2445.png">









-> Now a prompt appears for confirmation that shows the list of softwares that we need to install and then click on OK for the installation starts.








<img width="1440" alt="installation conformation" src="https://user-images.githubusercontent.com/112545596/190476685-4b36ab70-2a92-49b8-9b5d-3d0bad0bbd5f.png">











<img width="1440" alt="install process-1" src="https://user-images.githubusercontent.com/112545596/190476756-c1cbb172-e014-4f8a-a6ff-a90a18a0cbb8.png">










<img width="1440" alt="install process-2" src="https://user-images.githubusercontent.com/112545596/190476858-461b7af9-d9b1-45c0-a9e6-6cd4b7ab62c9.png">










<img width="1440" alt="install process-3" src="https://user-images.githubusercontent.com/112545596/190476898-e6a19ebb-c96c-4fa4-94fd-1cae440cc0c5.png">









-> Now after completion of the installation we need to reboot the Pi.








<img width="1440" alt="reboot" src="https://user-images.githubusercontent.com/112545596/190477927-991b5688-c0ef-4582-9ba1-1e5bc4398cf2.png">








## 4.Setup of the Postgres

-> Now run the command so that it navigates you to postgres@dietpi:/root
            
            sudo su postgres
            
-> Create a user and then connect to the postgres and then create a database
            
            createuser pi -P --interactive
            // enter the password that we had set it and for superuser u will enter no and for create new database and create new roles we will enter yes
            
           // for connection and create database
           
           psql
           create database test;
           
           
           
-> Now exit from the Psql shell by pressing control+D twice and now you enter into the pi user( root@dietpi) and login back into the postgres shell by using these commands
           
         sudo su postgres
           
         psql test

         create table people (name text, company text);
         
  
   
   
   
   
   
  <img width="1440" alt="postgres" src="https://user-images.githubusercontent.com/112545596/190494027-272b2118-1009-48cd-823a-e31db3fba651.png">









-> Now add data into the table 'people'
         
         insert into people values ('Jaswanth', 'Raspberry Pi Foundation');

         insert into people values ('Rama', 'Red Hat');
         
-> test that the data persists:

         select * from people;







<img width="1440" alt="postgresql result" src="https://user-images.githubusercontent.com/112545596/190495576-1a346091-045c-4d96-9d01-0811c3bedf2b.png">









# 5. NODE-RED

-> Go to your prefered browser and type http://your_RPI_IP_Address:1880

-> In browser popping up we can see node-red domain on the website which should look like this:
       
       http://192.168.8.198:1880
       
 
 
 
 
 
 <img width="1440" alt="NODERED" src="https://user-images.githubusercontent.com/112545596/190501271-d23be699-51ee-47c5-b6de-5f47942014ea.png">







-> Install node-red-contrib-re-postgres in terminal

         npm install node-red-contrib-re-postgres
         
         
         
         
         
         
   <img width="1440" alt="npm" src="https://user-images.githubusercontent.com/112545596/190501720-d6026cec-dac6-43a9-bbc8-d69634c3e017.png">









-> The node-run has the updated version and the command to update is given below:

         npm install -g npm@8.19.2
         
         
         
         
         
         
         
 <img width="1440" alt="npm update" src="https://user-images.githubusercontent.com/112545596/190502995-3334f23a-bb30-4ca7-b2fe-1d5c30cd2dce.png">








-> Restart node-red with the command

      dietpi-services restart node-red
      
      
      
      
      
      
  <img width="1440" alt="restart" src="https://user-images.githubusercontent.com/112545596/190503434-3abb3195-5a61-431c-8b84-b40684212a19.png">








-> After restarting node-red command go to the node-red web interface and go to manage pallete and select install module category and install 

            node-red-contrib-postgresql







<img width="1440" alt="node install" src="https://user-images.githubusercontent.com/112545596/190505731-eee5844c-574a-4db5-85bf-694d4c10dac8.png">








-> Now we are going to search and pull trigger, template, Postgres and debug nodes from the top left search panel in the node-red web interface
   later on wire the nodes in the given order.
   
            trigger->template->Postgres->debug

-> After establishing the connections it would be in this order










<img width="1440" alt="chart" src="https://user-images.githubusercontent.com/112545596/190507786-8b0d1916-0f14-4b33-bdb1-e795d24faa66.png">






