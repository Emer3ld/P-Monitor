# Plant-Monitor
###We have been set tasks to create a plant monitoring device using code already provided by the course tutor. An additional part of this task is to incorporate an additional way of adding elements to monitor our plant system. I have chosen to add the function of LED lighting to decipher the plant's most basic needs. Naming the plant monitoring device Chroma Lumiere is based on the concept of chromatophores a colour-changing plant pot where changing colours of light are translating what the plant needs on the fundamental requirements i.e. light, Water and humidity.

###The tools and code we need for our plant monitoring system in order are:
-1.Installation and setup of Arduino IDE
-2.AdaFruit Feather Huzzah code(MQTT).
-3.Plant monitor setup.
-4.Installation of Raspberry Pi iOS(for Mac users).
-5.Specifications for setting up Influx DB using shell, I will include a troubleshooting folder.
-6.Installing Grafana.
-7.Code for LED lights
8.3D printing file
9.PPTX

Items needed for plant monitor.

•	1x Feather Huzzah	•	1x Plant shield
•	2x Nails,	•	1x plant (to monitor)
•	2x Wires	•	1x DHT22 (Temperature and humidity sensor)
•	1 x Shell	•	4x resistors
•	1x Moisture	•	1 x set of plyers
•	1x Base	•	1x Wire cutter

Methods- Soldering 

Our plant monitors were created using 2 nails as capacitors and a 3D base and shell that protects our huzzah.

First, we will look at a brief diagram of how we will wire our plant monitor and how it applies to the baseboard. 

 


<img width="437" alt="image" src="https://user-images.githubusercontent.com/114082509/201496025-1022d0db-dc8c-4291-8ee7-e0eedd1bc7f1.png">














We will now place all the resistors on the cover board using this diagram. We will solder the components i.e. resistors and DHTT sensor.


<img width="335" alt="image" src="https://user-images.githubusercontent.com/114082509/201496032-47c79c9d-4a03-4b77-b36d-fdb21486413f.png">



 

From my design, I’m not sure if wrapping will cause a longer delay in receiving readings…. Maybe you could create it without the binding but I like the contrasting colours against the yellow base. I also soldered the wires to the top of the nails to prevent corrosion. Although corrosion is inevitable I believe adding an oil coating or acrylic will prevent us from receiving accurate readings but we can always replace the nails if we start to see inaccurate readings.

<img width="424" alt="image" src="https://user-images.githubusercontent.com/114082509/201496043-29952246-cae3-49e5-9c4d-1ea3e6c45556.png">

 

When we have completed putting our plant monitors

Connecting to Mqtt Explorer

We will check the serial monitor to show if we are receiving data, as you can see my readings are being produced every minute at the fastest rate of 115200 baud sending dater by 12800 bytes per second.

<img width="333" alt="image" src="https://user-images.githubusercontent.com/114082509/201496057-2bc9c3e8-ce82-44ef-8253-c184bd28b7ef.png">

 

As you can see on Mqtt explorer, my topic is displaying the variables of temperature, humidity and moisture.


 <img width="413" alt="image" src="https://user-images.githubusercontent.com/114082509/201496067-014e2263-4c4b-440b-9f14-4ff5282a0670.png">







