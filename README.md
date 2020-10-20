# Simple Home Assistant Automation to enable Shelly Duo lights in Sequence
The instructions below can be used to configure a Shelly Duo without configuring a Shelly account using the stock firmware. 

Prerequisites:
- You already have an MQTT server up and running

### Connect your Shelly Duo bulbs

  - Power on the Shelly Duo bulb
  - Connect with your phone or laptop to the shelly wifi network
  - Instead of configuring though the app, use your preferred browser and go to http://192.168.33.1
  - Go to "Internet & Security" -> "Wifi mode - Client" - and configure your home network credentials
  - (Optional, but recommended) Assign a static IP Address to your bulb

### Configure MQTT on your Shelly Duo bulbs

  - Make sure your bulb is connected to the network your MQTT server is available on
  - Use your preferred browser and go to the IP address of your bulb (Check your DHCP / Static address)
  - Go to "Internet & Security" -> "Advenced - Developer Settings" - and configure your MQTT Settings
  - (Optional) Set a custom prefix for your bulb, you'll thank me later
 
### Add Automation to Home Assistant
- Use the automation in scripts.yaml and add it to your own configuration
- Edit the ``` topic: shellies/ShellyDuoBulb1/light/0/set ``` 5 times. 
- (The part behind "shellies/" is the optional custom prefix. If you did not set any, it will be something like "shelly-<deviceid>")

If all went well, you now have an awesome sequence to turn on your light bulbs!
