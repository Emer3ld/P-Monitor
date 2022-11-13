# Plant-Monitor
### We have been set tasks to create a plant monitoring device using code already provided by the course tutor. An additional part of this task is to incorporate an additional way of adding elements to monitor our plant system. I have chosen to add the function of LED lighting to decipher the plant's most basic needs. Naming the plant monitoring device Chroma Lumiere is based on the concept of chromatophores a colour-changing plant pot where changing colours of light are translating what the plant needs on the fundamental requirements i.e. light, Water and humidity.


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

![image](https://user-images.githubusercontent.com/114082509/201524471-d12c3fd6-ce14-4691-9ab1-364e6a8eb666.png)
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






### Additional design and code to be added
- LED light
- 3D warp tunnel to be printed(see file in Setup)
