<details><summary>Calibrating steps per mm</summary>
  - [Reprap](https://reprap.org/wiki/Triffid_Hunter's_Calibration_Guide)
</details>

**>** [Pressure Advance tutorial](https://boxnovel.com/novel/castle-of-black-iron/chapter-1785)

**>** [Z Stepper in series adapter DYI instructions](https://www.instructables.com/id/Wiring-Your-Z-Stepper-Motors-in-Series/")

**>** [Filament drier temperatures](https://www.printdry.com/how-to-dry-filaments/)  ([local copy](https://github.com/vladbabii/3d_printing/blob/master/docs/dry_temps.md))

**>** [Calculate Klipper steps per mm](https://jsfiddle.net/wladq66/ejyh489t/21/)


<details><summary>Optimal layer height</summary>

>  My understanding of it is you want to use multiples of a full step as layer heights when using leadscrews. So if you have 1.8 deg motors then you get 1 revolution for 200 steps, which moves the axis 8mm. 8/200 = 0.04mm or 40 microns.

> So you can use 0.04, 0.08, 0.12, 0.16, 0.20, 0.24, 0.28, 0.32, 0.36mm layer heights with a 0.4mm nozzle. That's a fair range of options. Can you use 25micron multiples, yes but you might get less than ideal prints if you have twin screws and twin motors which might go out of sync when they stop between full steps.

[source](https://reprap.org/forum/read.php?1,741639,741693#msg-741693)
</details>


<details><summary>Probe Accuracy</summary>

- [Z Probe Micro Switch Shoot Out! How Accurate Are They For 3D Printing? + Hall Probe testing](https://www.youtube.com/watch?v=BLzCeH1hS9g)
- [Autoleveling on 3D printers: 9 myths and 12 sensors tested!](https://www.youtube.com/watch?v=il9bNWn66BY&feature=youtu.be)

</details>

<details><summary>How to set z probe height</summary>
i calibrate the z offset by heating up the bed first
  
then doing the calibration

after that i repeat these steps:

- bed temp set to normal printing temp

- nozzle set to normal printing temp

- home all then probe middle of print surface

- go to G0 Z2

- lower the printhead little by little until it hits a piece of paper put on the bed

- increase/decrease z_offset

- save config

- go to first step and repeat until when doing G0 Z0 the distance seems perfect in relation with the piece of paper

- do a quick print (only first layer)

- either adjust z offset and/or flow for material

- when satisfied, do a couple of first layer prints to insure repeatability

once that is done i do the mesh bed leveling part and save the mesh then make sure the mesh is loaded in startup gcode in the slicer

before each print i repeat the first few steps from calibration procedure: bed temp, nozzle temp, home axes, probe middle

this makes sure that mechanically i do the same things at start of each print so if there are any z wobble or other mechanical imperfections they are done exactly the same every time

</details>




<details><summary>How to unclog heatbreak</summary>
  
how i inclogged blocked heatbreaks
1. soldering  iron
2. dremel drill bit pack - the 1.2 mm drill bit
steps:
set your soldering iron to at least 300 c
and touch the hotend-side of the heatbreak to the tip
once it gets hot enough
carefully place your soldering iron somewhere safe
while holding heatbreak with pliers,  quickly insert the drill bit, wait for a couple of seconds then pull
clean the drill bit and repeat as many times as needed, sometimes just pulling and sometimes rotating it
doing it by hand is fine
if you use a power tool you risk gouging the insides of the heatbreak
</details>





<details><summary>Calibrating maximum volumetric rate</summary>
  
Source: http://projects.ttlexceeded.com/3dprinting_calibrating_volumetric_rate.html
  
Test procedure
Here’s how I’ve set up my testing:

I’m printing with eSun PLA+ filament with a nominal diameter of 1.75mm with a cross-section of roughly 2.405mm.

I’m running an OG R2 (April 2018) extruder setup.

G-code commands are sent directly to the printer using Octoprint running on a Raspberry Pi connected via USB.

To do testing, fire up Pronterface or Octoprint connected to your 3D printer via USB and begin issuing manual g-code commands.

First, set extruder mode to relative and set my nozzle temp to 200C and began extruding using eSun PLA+:
```
M83
M109 S200
```
Then begin issuing commands to extrude 60mm of filament at different speeds:

```
G1 E60 F300
G1 E60 F400
```
Increment speeds by 100mm/min (the Fxx parameter) until you the extruder clicking.

Reduce by speed by 50mm/min.

Increment upward by 10mm/min until you hear the extruder start to skip again

Backed down by 5mm/min.

Once you find the highest speed that extrudes without extruder clicks, repeat the test 2 more times for verification.

Once you determine the speed for a particular temperature, the calculations are simple:

Divide the speed used in the G1 command by 60 to convert mm/min to mm/s.

Multiply the speed in mm/s by the area of the cross-section of my 1.75mm filament (2.405) to get the corresponding rate measured in mm3/s .

Reduce the measured rate (.5 mm3/s is a good amount) to leave some headroom for hardware and filament variations.
</details>
