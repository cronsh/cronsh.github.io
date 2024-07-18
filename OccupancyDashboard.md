[Home page](README.md)

## Simple Occupancy Dashboard for AOA crossline counting 

![Example of Dashboard](https://github.com/cronsh/cronsh.github.io/blob/main/AOA_Crossline_occupancy_NR_Dashboard.jpg?raw=true)

### Description:
 When a customer wants a simple dashboard for displaying the current occupancy of an area e.g. carpark or retail store. To achieve this you need to create two AOA crossline counting scenarios (in & out). Currently for single entrance only but could be adapted for more.

### Typical use cases:
Counting humans or vehicles in/out of an entrance to obtain & display occupancy value . e.g. carpark, store, office etc.

### Required Components
- Camera suitable for running AOA crossline counting
- MQTT Broker e.g. Mosquitto / NodeRED
- NodeRED

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

![image](https://api.aintegration.team/image/custom-analytics)
