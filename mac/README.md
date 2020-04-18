# 3D Printer Software (MacOS)
** Disclaimer: this is a collection of open source software and I am not the original creator. These are simply copies that I use on my specific machine (minor changes to deprecated version).


```
.
├── GrblController.app
├── GrblController2.app
├── README.md
└── grbl
    ├── config.h
    ├── coolant_control.c
    ├── coolant_control.h
    ├── cpu_map.h
    ├── defaults.h
    ├── eeprom.c
    ├── eeprom.h
    ├── examples
    │   ├── grblUpload
    │   │   ├── grblUpload.ino
    │   │   └── license.txt
    │   └── grblWrite_BuildInfo
    │       ├── grblWrite_BuildInfo.ino
    │       └── license.txt
    ├── gcode.c
    ├── gcode.h
    ├── grbl.h
    ├── jog.c
    ├── jog.h
    ├── limits.c
    ├── limits.h
    ├── main.c
    ├── motion_control.c
    ├── motion_control.h
    ├── nuts_bolts.c
    ├── nuts_bolts.h
    ├── planner.c
    ├── planner.h
    ├── print.c
    ├── print.h
    ├── probe.c
    ├── probe.h
    ├── protocol.c
    ├── protocol.h
    ├── report.c
    ├── report.h
    ├── serial.c
    ├── serial.h
    ├── settings.c
    ├── settings.h
    ├── spindle_control.c
    ├── spindle_control.h
    ├── stepper.c
    ├── stepper.h
    ├── system.c
    └── system.h
```

## My Setup Instructions:
### GRBL on Arduino
I use an unofficial arduino nano. Most boards will work as long as they are 328p-based.

1. Clone this repository
2. Open the Arduino IDE
3. Go to `Sketch > Include Library > Add .ZIP Library...` 
4. Find the `grbl` folder from my repository and select it
You should now see `grbl` in the dropdown menu of `Sketch > Include Library`
5. Go to `File > Examples > gbrl > grblUpload`
6. Plug in the Arduino as usual and upload the sketch

### Visual Software
For passing the g_code designs to the printer via serial, I use GrblController. It's pretty much a deprecated project now and it's a bit tough to find online so I'm going to leave the two built versions that I use here (`GrblController.app and GrblController2.app`). There are only a few settings to tweak here that I will update later.
