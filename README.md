# diy_sonoff_miniR3
HOWTO SonOff Mini R3 DIY Mode

# Turn SonOff Mini R3 in DIY Mode
## Start AP on MiniR3
Keep pressing the button until the light flashes differently (2 short and one long), release. Again, keep pressing to switch to DIY mode, the light should blink quickly.
## Connect to AP
Connect to the new wifi network available with the name "ITEAD-XXXXXXXXXX" with the password 12345678. Take note of the value of "XXXXXXXXXX", this represents the device id, it will be needed to order the module.
## Configuration of the wifi network on the module
Once connected to the "ITEAD-XXXXXXXXXX" wifi network, you must go to the address "http://10.10.7.1". You must then enter the information of your wifi network and restart the device.
## Time to switch
After finding the ip address assigned to the device, you can send the commands to change the state of the switch.
```bash
curl -X POST -H 'Content-Type: application/json' -d '{"deviceid":"XXXXXXXXXX","data":{"subDevId":"123456","switches":[{"switch":"off","outlet":0}]}}' http://192.168.0.46:8081/zeroconf/switches
curl -X POST -H 'Content-Type: application/json' -d '{"deviceid":"XXXXXXXXXX","data":{"subDevId":"123456","switches":[{"switch":"on","outlet":0}]}}' http://192.168.0.46:8081/zeroconf/switches
```
The "subDevId" parameter is arbitrary

