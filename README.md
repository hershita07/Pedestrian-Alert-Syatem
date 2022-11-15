# Pedestrian-Alert-System

## Requirements

Software: pytorch,CUDA  
Computational Environment: Edge cloud  
Hardware:  
* On Board Units (consisting GPRS module, 802.11p radio module, WiFi module, GPS module, Bluetooth module,accelerometer,gyroscope)  
* Road Side Units(consisting GPRS module, 802.11p radio module, WiFi module, GPS module, Bluetooth module)  
* IP camera            
 
## Experiments

Detection using deep learning algorithms and processing data over the cloud followed by broadcasting information like position of the pedestrian to the nearby vehicles hence with an alert app connected to OBU via RN4020 bluetooth module,we could alert the driver.
* STEP 1 :     
Using RTSP(Real Time Streaming Protocol) the data in terms of frames was taken from the IP camera. Using YOLOv5 algorithm detection was done and with the creation of bounding box in the region of interest the serial data was taken in terms of a flag value. 
* STEP 2 :   
The flag value was then updated over a csv file on the edge cloud which was being copied on to the RSU continuously. 
* STEP 3 :
The RSU was broadcasting the information in terms of packets to the OBUs in range. As soon as the OBU was detecting the relevant flag value in the recieved packets it gave the alert via bluetooth to the app.  
<p align="center" width="70%">
    <img width="33%" src="https://github.com/hershita07/Pedestrian-Alert-System/blob/main/app.png">    
</p>

 

The connection via blutooth to the app did decrease the time delay that is usually faced in telegram alert generation.  
The detection algorithm being deployed ove a camera at some height,did bring up challanges in false detections sometimes. 
