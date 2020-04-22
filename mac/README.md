# 3D Printer Software (MacOS)
** Disclaimer: this is a collection of open source software and I am not the original creator. These are simply the versions I used and slightly modified to fit my requirements.


```
.
├── GrblController.app
├── GrblController2.app
├── README.md
├── gcode_parser
└── grbl
    └── Lot's of stuff . . .


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
For passing the g_code designs to the printer via serial, I use GrblController. It's pretty much an archived project now and it's a bit tough to find online so I'm going to leave the two built versions that I use here (`GrblController.app and GrblController2.app`). There are only a few settings to tweak here that I will update later.

### Slicing
You will need to use a slicer if you plan on using CAD software like AutoCAD which does not export g_code directly. I'm using Slic3r since it's simple and free.

Eventually, I'll upload a settings file here for anyone to replicate my setup.

## Idea Time | What to do
1. Make a drawing in CAD (I use AutoCAD 3D now)
2. Export to an .stl file
3. Import .stl to Slic3r and specify printer/filament/print settings
4. Export g_code
5. Run my script: `gcode_parser` to correct small g_code commands that are different on my printer
6. Open the new g_code file in GrblController
7. Use the command `S1000` in GrblController to set the "spindle" speed to max
8. Hit `spindle on`, pause, then `spindle off` (this starts heating the 3d pen)

### gcode_parser script
Run it with:
```
# Run chmod +x gcode_parser if necessary
./gcode_parser <path to slic3r's gcode output>
```
It makes the following modifications:
1. Changes all `G1` to `G01` for XYZ commands
2. Changes all `E0` to `M05` to turn off the extruder
3. Changes all `EXX.XX` to `M03` to turn on the extruder
4. Inverts all X and Z positions (negative/positive directions swap)

