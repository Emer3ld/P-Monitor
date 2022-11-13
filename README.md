# Plant-Monitor
### We have been set tasks to create a plant monitoring device using code already provided by the course tutor. An additional part of this task is to incorporate an additional way of adding elements to monitor our plant system. I have chosen to add the function of LED lighting to decipher the plant's most basic needs. Naming the plant monitoring device Chroma Lumiere is based on the concept of chromatophores a colour-changing plant pot where changing colours of light are translating what the plant needs on the fundamental requirements i.e. light, Water and humidity.

I initially chose the Aglaonema Red Star in CE-Hub and then my Agave cactus to test at home. They both have a striking appearance and a sensitivity to light which would give me more variables to work with. You might ask why two plants? There weren’t enough plants to go around so I will use my own agave plant for most of my results. However, I will include the Aglaonema red Star as it was in my initial design idea.


### The tools and code we need for our plant monitoring system in order are:
- 1.Installation and setup of Arduino IDE
- 2.AdaFruit Feather Huzzah code(MQTT).
- 3.Plant monitor setup.
- 4.Installation of Raspberry Pi iOS(for Mac users.

- 5.Specifications for setting up Influx DB using shell, I will include a troubleshooting folder
- 6.Installing Grafana.
- 7.Code for LED lights
- 8.3D printing file
- 9.PPTX


<img width="548" alt="image" src="https://user-images.githubusercontent.com/114082509/201534200-a6fb8ccf-36ac-4acd-89f2-85c5b014197e.png">


## Items needed for the plant monitor.

- 1x Feather Huzzah	
- 1x Plant shield
- 2x Nails,	
- 1x plant (to monitor)
- 2x Wires	
- 1x DHT22 (Temperature and humidity sensor)
- 1 x Shell	
- 4x resistors
- 1x Moisture	
- 1 x set of plyers
- 1x Base	
- 1x Wire cutter


## Methods- Soldering 

Our plant monitors were created with using 2 nails as capacitors and a 3D base and shell that protects our huzzah.

First, we will look at a brief diagram of how we will wire our plant monitor and how it applies to the baseboard. 

 <img width="320" alt="image" src="https://user-images.githubusercontent.com/114082509/201525245-d621df5b-f977-450d-ac35-65199e41a4aa.png">     <img width="257" alt="image" src="https://user-images.githubusercontent.com/114082509/201525251-d17a6df3-b69e-47c7-ab3f-1acc81e1fb3c.png">


We will now place all the resistors on the cover board using this diagram. We will solder the components i.e. resistors and DHTT sensor.


  <img width="314" alt="image" src="https://user-images.githubusercontent.com/114082509/201525374-9fa5e8cb-2852-4750-8af9-b8592985dc74.png"> <img width="289" alt="image" src="https://user-images.githubusercontent.com/114082509/201527952-10e5bd10-2c9e-4166-a800-f28c24d76332.png">



From my design, I’m not sure if wrapping will cause a longer delay in receiving readings…. Maybe you could create it without the binding but I like the contrasting colours against the yellow base. I also soldered the wires to the top of the nails to prevent corrosion. Although corrosion is inevitable I believe adding an oil coating or acrylic will prevent us from receiving accurate readings but we can always replace the nails if we start to see inaccurate readings.
 
When we have completed putting our plant monitors the should resemble above

Connecting to Mqtt Explorer

We will check the serial monitor to show if we are receiving data, as you can see my readings are being produced every minute at the fastest rate of 115200 baud sending dater by 12800 bytes per second. As you can see on Mqtt explorer, my topic is displaying the variables of temperature, humidity and moisture.


<img width="552" alt="image" src="https://user-images.githubusercontent.com/114082509/201525543-ab90767c-c135-4d31-9441-bb4c1e75386c.png">



I will provide a step by step set of instruction along with some troubleshooting pages to create an LED plant monitor. 
Starting with:


After installing the Arduino IDE  we will need to install several libraries and the board managers.
Select the ‘Tools’ menu the select board manager from that menu you will be able to search for “ESP8266” board,
Make sure your parameter are set to all to increase your possibility of finding the correct package by the “EP8266 community”

Next we will install the Eztime library, which is available on GitHub here. The EZtime library is needed to connect to the Network Time protocol using the waitForSync function. You can download the rest of the code.

The next Library to install is the PubSubClient, this page all also guide you through the installation in which we will pull the file through the Arduino IDE how to get the our data through to the MQTT server, there are many to choose from but we will look at MQTT Explorer and later Influx DB.

<img width="241" alt="image" src="https://user-images.githubusercontent.com/114082509/201530033-aa9cd4aa-49d5-49ef-a16c-ddf4bdc15fc9.png">
 
Now we will connect our Huzzah to the Wi-Fi but first we will need to include our downloaded library to the code, which will follow the notation of ESP8266WiFi.h a header file extension, listing everything.

- #inlcude <ESP8266WiFi.h>
- const char* ssid	= “SSID”;
- const char* password = “password here”;
- const char* host  	=”iot.io”;

After downloading the PubSub client you can now use the code in the GitHub repository to complete the rest of the setup.

## Using the Pi terminal and isntalling  InfluxDB and Grafana

To install Influx DB and Grafana via our Raspberry Pi we will use the initial setup in the terminal.
After we have installed Raspberry pi imager we will open the terminal (for Mac users and PuTTy for windows). We will type “ssh”(secure shell protocol) and the username we chose and stored in the imager to write to our SD card.
ssh pi*youUserName.local. 
This will be your host name and remember to keep tab of your password. The next step will assimilate your name and your IP address:
Sudo nano/etc/hosts
This will open a GNU file where it will allow you to make the change to the original code. Where 127.0.1.1 is stated you will change the original host name to your hostname.
An update is needed to verify the changes:
Sudo apt update
Sudo apt upgrade -y
Reboot
To instal Influx DB (Ubuntu & Debian(ARM 64-bit) we will now need to enter the command
Sudo apt-get update && sudo apt-get-install influxdb2 

<img width="514" alt="image" src="https://user-images.githubusercontent.com/114082509/201533684-e410a726-f4ab-4227-8d58-be22de474344.png">
    

We will need to copy and paste the and run another update to fully install InfluxDB with our key using this command:

Sudo apt-get update
Sudo apt-get install influxdb2 -y

After this has installed we will type in http://YourUserName.local:8086 into your browser of choice and follow the instructions for setup.

After creating our MQTT bucket in Influx DB  we can now install Grafana to visualise our data.
Installing Grafana’s setup is very similar to installing InfluxDB, still using terminal


<img width="514" alt="image" src="https://user-images.githubusercontent.com/114082509/201533720-d5301542-3493-45d3-afca-1223650362ff.png">


We will copy the sudo just like we did for the above.

Grafana should now be installed, the following code will now be needed to start up Grafana.

sudo	/bin/systemctl daemon-reload
sudo	/bin/systemctl enable grafana-server
sudo	/bin/systemctl start grafana-server

Enter http://yourusername.local:3000/ into your browser where you will see the default page then enter 
Username : admin
Password: admin
To have your data feed through from InfluxDB, you need to set up your query language 'Flux' and add the URL you used to access InfluxDB. 
-	Switch of the option of basic auth
-	Add you influxDB API token
-	Set MQTT-data as you originally set up in Influx DB.
From there you can create a new dashboard and visualise you data.
	
Make sure you select the correct bucket intially in Grafana if you can't find any data displaying head back to InfluxDB and search through your most recently created buckets, if the name of the bucket differes slightly ammend it to correlate with what you are seeing in Grafana.

### Additional design and code to be added
- LED light
- 3D warp tunnel to be printed(see file in Setup)

## References
[^1]: Arduino IDE setup images [^1]
[^2]: Raspi config troubleshooting pages seedstudi.com[^2]
[^3]: CE-Hub Plant monitor setup instructions, code & schematics- Duncan Wilson 2022.[^3]
[^4]: Plant casing and Dhruv Kumar 2022.[^4]
[^5]: Influx DB image instalation page. [^5]
[^6]: Grafana image instalation page. [^6]
