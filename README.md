# SmartSense-Motion-Sensor-Temperature-Edit
Files and instructions on how to edit SmartSense Motion Sensor to show temperature on the dashboard instead of motion, while containing still all the information under detailed view.

###### Way 1:
Create new Device Handler at [SmartThings IDE](https://graph.api.smartthings.com/).  
Copy all the code from [here](/devicehandler.txt) to the device handler and you are good to go.

###### Way 2:
Create new Device Handler using the SmartSense Motion Sensor template.  
Copy your UUID from the device handler URL. https://graph.api.smartthings.com/ide/device/editor/UUID-is-here  
Use the SmartThings CLI to generate a json file of the presentation with:
```
smartthings presentation:device-config:generate UUID --dth --output=presentation.json
```
Edit the .json file to match [input.json](/input.json) and run:
```
smartthings presentation:device-config:create --input=presentation.json
```
Then copy the mnmn and vid fields to your device handler metadata definition field. [Example here.](/devicehandler.txt)  
Also add ocfDeviceType: "oic.d.thermostat" to change the icon to thermostat.