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
