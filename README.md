<details><summary>Calibrating steps per mm</summary>
  - [Reprap](https://reprap.org/wiki/Triffid_Hunter's_Calibration_Guide)
</details>

**>** [Pressure Advance tutorial](https://boxnovel.com/novel/castle-of-black-iron/chapter-1785)

**>** [Z Stepper in series adapter DYI instructions](https://www.instructables.com/id/Wiring-Your-Z-Stepper-Motors-in-Series/")

**>** [Filament drier temperatures](https://www.printdry.com/how-to-dry-filaments/)  ([local copy](https://github.com/vladbabii/3d_printing/blob/master/docs/dry_temps.md))


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
