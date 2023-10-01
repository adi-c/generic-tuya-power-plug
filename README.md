# generic-tuya-power-plug
 Information on generic tuya power plug with monitoring.

 Name: Tuya 16A 20A EU Smart Socket WiFi Smart Plug With Power Monitoring
 Aliexpress Link: [here](https://www.aliexpress.com/item/1005005374840269.html?spm=a2g0o.order_list.order_list_main.25.83be1802E3a6GU#nav-description)

 Device: ESP8285
 Device board: AJW-02_8285

 Notes: The plug does not ahave any inscription that can be used to identify a brand name or a model.

 ## Opening the plastic box
 Just insert a precision screwdriver in one of the grounding tabs and pry it by pressing down on the handle
![plug_box](https://github.com/adi-c/generic-tuya-power-plug/blob/master/images/20231001_220302.jpg?raw=true)

 ## Soldering the wires
Solder a wire to GPIO 0 on the top side of the plug PCB. This one needs to be shorted to GND when powering the device.
![top_side](https://github.com/adi-c/generic-tuya-power-plug/blob/master/images/20231001_220414.jpg?raw=true)

Solder 4 additional wires according to the picture below (Please ignore the broken tab on the TX pin :)):
![bottom_side](https://github.com/adi-c/generic-tuya-power-plug/blob/master/images/20231001_220429.jpg?raw=true)

Connect all the wires:

| Smart Plug  | USB-TTL converter |
| ------------- | ------------- |
| GPIO 0  | GND  |
| 3v3  | 3v3  |
| GND  | GND  |
| RX  | TX  |
| TX  | RX  |

Please make sure your USB-TTL converter works on 3.3V

## Install firmware and configure

Install the Tasmota firmware using the tool of your choice. I used https://tasmota.github.io/install/ 

Configuration Template: 

```json
{"NAME":"Generic 20A Power Monitoring Plug","GPIO":[1,1,1,32,2720,224,1,1,1,320,289,1,1,1],"FLAG":0,"BASE":18}
```

