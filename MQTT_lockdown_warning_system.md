[Home page](README.md)

## How to create a simple MQTT lockdown / warning / notification system 

{% [Example of Dashboard](https://github.com/cronsh/cronsh.github.io/blob/main/AOA_Crossline_occupancy_NR_Dashboard.jpg?raw=true) %}

### Description:
 This setup can be used to create a simple auidible/visual warning or notification system. By using MQTT protocol it makes configuration simple and is ideal for mass triggering of multiple devices.

### Typical use cases:
This can be used for a variety of mass warning / notification use cases you only need to use your imagination. Depending on your operational requirements it could ideally suited to a lockdown system.

### Required Components
- Trigger device: This can be anything from a simple panic button, keypad, intruder panel, or can can trigger a NO / NC output to change state.
- MQTT publisher (used in conjection with trigger device) - If the trigger device supports MQTT no additional equipment required. However, in my example i am using a simple panic button connected to the Axis A9210 network IO (which has MQTT support)
- Output device: Any Axis speaker, Axis audio bridge/amp, Axis D4100 strobe siren, or any other output device that supports MQTT.  
- MQTT Broker e.g. Mosquitto, NodeRED, HiveMQ etc.

### Things to consider
- Make sure all the prerequisites for AOA are met for accurate counting of objects.
- This is an estimation of occupancy only. I have included a way of manually editing the occupancy figure to correct missed counts if required.
- Reset count to zero button also included.

### System overview
- Crossline counting value outputted from the cameras two AOA scenarios using MQTT
- NodeRED extracts the relevant data and stores in context data flow.
- Using a function node one value is subtracted from the other to provide the occupancy figure. 
- This is then outputted to a gauge dashboard node

### NodeRED Flow
![Example Flow](https://github.com/cronsh/cronsh.github.io/blob/main/AOA_Crossline_occupancy_NR_Flow.jpg?raw=true)

## Download NodeRED flow 

[Click to download flow](https://github.com/cronsh/nodered-flows/blob/main/Axis-AOA-Crossline-counting-dashboard/AOA_Crossline_occupancy_NR_Flow.jpg)
