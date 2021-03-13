---
layout: post
title: Keeping my plant alive
date:   2021-3-8 20:26:58 -0700
categories: random work
---

I program a microcontroller to send a notification once my plant needs to be watered.

...Because I can barely take care of myself, much less another living thing.

## The setup
**Equipment:**
* The [Sparkfun Soil Moisture Sensor](https://www.sparkfun.com/products/13637?_ga=2.235359937.1768061677.1615260007-2127130474.1613147809), a tiny breakout board with two conductive pads that create variable resistance/signal.
* The [Sparkfun Photo RedBoard](https://www.sparkfun.com/products/13321?_ga=2.260386509.1768061677.1615260007-2127130474.1613147809), a dev board/microcontroller that's compatible with [Particle's web IDE](https://www.particle.io/developer-tools/).
* A couple [jumper wires](https://www.sparkfun.com/products/11026?_ga=2.90123739.1768061677.1615260007-2127130474.1613147809), since I got the moisture sensor with screw terminals.
* My [silver pothos](https://en.wikipedia.org/wiki/Scindapsus_pictus) house plant.

**Circuit:**  
* Sensor vcc -> d7 (digital) 
* Sensor sig -> a2 (analog)
* Sensor gnd -> gnd

**Code:**
Started from [this file](https://github.com/sparkfun/Inventors_Kit_For_Photon_Experiments/blob/master/03-PlantMonitor/Code/02-InternetHouseplantMonitor/InternetHouseplantMonitor.ino) written by Joel Bartlett, and made the following modifications:
```
int watering_state = false;// Added a temporary state to capture whether the plant needed watering.
.
.
.
void loop() //begin loop
.
.
.
delay(86400); //Ramped up the delay to run moisture checks daily. 
// Prevents me from getting spammed if I don't water the plant. For testing, set to 10000: 10 secs.

    if(readSoil() < 2000)
    {
      state = true;
    }
    else
    {
      state = false;
    }
    //Tweak if/else statements to adjust state according to the readings.
    //Calibrated to the pothos' preferred moisture level (~2000 on the serial reading).
.
.
.
//Added an if statement in the loop that would publish an event based on the watering state.
    if(watering_state)
    {
        Spark.publish("plantMoistureState", "Dry", 60, PRIVATE);
        delay(5000);
    }
```
## It's alive!

I plugged my board into my mac, ran a scan to find the correct serial port (` ls /dev/tty.*`), and connected to the board using a screen command (`screen /dev/tty.[port_name] 9600`).

After verifying that the board read could correctly read some basic values, I stuck it into the soil of my silver pothos.

![sensor embedded in plant soil](https://raw.githubusercontent.com/svvchen/nervxious/gh-pages/assets/images/sensor_in_plant.jpg)

Here's the basic readout from my serial port. Low at first, since the sensor is outside the soil; high later on, once placed in the soil.

![readout from serial port](https://raw.githubusercontent.com/svvchen/nervxious/gh-pages/assets/images/readout.png)

## Putting it to use...

After verifying that the sensor worked, and playing around with moisture settings, I was ready to create my email notification. I did using [If This Than That](https://ifttt.com/home), a platform that allows developers to trigger and monitor events across apps.

Setup was pretty straightforward: create an account, and set up an event trigger.
![plant event in IFTTT](https://raw.githubusercontent.com/svvchen/nervxious/gh-pages/assets/images/if_then_1.jpg)

Then, hooking it all up: I switched the board on, flashed the code, and dried off my sensor...
![email in inbox reminding me to water plant](https://raw.githubusercontent.com/svvchen/nervxious/gh-pages/assets/images/please_water_1.jpg)

Huzzah! I'll still need to configure some settings (moisture levels), but it works!

Maybe, just maybe, I'll keep this one alive. 🌱🤞
