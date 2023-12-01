<br/>
<p align="center">
  <h3 align="center">Voron Trident Belted Z</h3>

  <p align="center">
    Belt all the things.
    <br/>
    <br/>
  </p>
</p>



## About The Project

![Screen Shot](images/genevamotion.jpg)

This `mod` is the combination of multiple ideas for belted system for the Trident Z motion. Most of the inspiration came from X0, which uses NEMA 17 gearboxes. The main goal was to use 9mm belts for Z motion while keeping most of the original Trident skirts and not relocating Z steppers to the top of the printer. We give credit to `bythorsthunder` for his [Orion belted mod](https://github.com/bythorsthunder/Orion-Tri-Belt), which has also been proven efficient and easy to assemble (the same applies to the [belted z motion](https://github.com/MathematicalPotato/Voron_Mods/tree/main/VT_Belted_Z) mod introduced by `MathematicalPotato`).

## General Info

The design offers two different options for the Z idlers:

MathmaticalPotato Idlers: 
 - Uses existing XY front idlers
 - Limited to ONLY 9mm wide pulleys (12mm overall width)
<p align="left">
  <img src="images/Potato Idler.png" width="200">
</p>


DoubleT XYZ Idlers:
 - Modified version of the Ramalama2 idler design
 - Z idler pulley integrated into XY idler
 - More flexibility in Z pulley width
<p align="left">
  <img src="images/DoubleT Idler.png" width="200">
</p>

Refer to the CAD drawing for detail on both Idlers.
BOM contains sections for both.

## Update History:
#November 30th 2023
 - V2 Beta idlers added

#October 12th 2023
 - Raised the bed standoffs on the carriages by 6mm.
 - This should improve compatibility with slimmer beds and most iterations of Tiny-T.
 - NOTE: Requires a change from M5x16 to M5x25 fasteners for the carriage to the bed frame.

#July 23rd 2023 
 - Added belt/stepper covers for inverted electronics by `Panzarkatten`

#July 3rd 2023:
 - Revised rear motor mount and idler.  Orientation of the motor turned 90 degrees. New idler replaces the rear bracing from Z extrusion to A/B drive extrusion
 - New front idler option added. Integrated the Z idler pulley into DoubleT's modified Rama idlers.
 - Cleaned up the CAD
 - Added motor skirts for 350mm build size

## Tiny-T considerations:
The Tiny-T supports the use of either MGN9 or MGN12 linear guides on the X axis.  This mod is compatible with MGN12 / Afterburner/Stealthburner style toolheads without modificaiton.
MGN9 based systems using V0.2 style toolheads will position the nozzle 5-6mm higher than AB/SB configurations.  This results in the bed being unable to reach the nozzle before colliding with the Z idlers. V3 Z carriages should resolve this travel limitation, but this assumes the use of a 6mm build plate with a 1mm magnet.  Magbeds may need additional spacing.

## Bill Of Materials

Required parts:
- 3 NEMA 17 Economy planetary steppers
	- [Ali Express](https://www.aliexpress.us/item/3256804434852612.html)
	- [Amazon](https://www.amazon.com/STEPPERONLINE-Planetary-Gearbox-Stepper-Printer/dp/B00WATUFIG)
- 9mm GT2 belts
- 3 9mm 20T GT2 drive pulleys, 8mm ID
- 3 9mm 20T toothed idlers, 5mm ID - Gates/Runice recommended. (Overall width of less than 14mm, Flange diameter less than 16mm)
- 9 M3x12 Button head screws (mounting gearmotors)
- 8 M3x30 Socket head screws (Front Motor Bracing, Rear Z carriage mounting)
- 2 M3x35 screws (Front Z belt tensioners)
- 1 M3x40 screw (Rear Z belt tensioner)
- 7 M3 heatset inserts (Front motor bracing, Z belt tensioners)
- 2 M5x35 screws and nuts (front idlers)
- 1 M5x25 screw and nut (rear idler)
- 1 5mmx30mm dowel (Rear Z Idler Shaft)
- 20 M5x10 screws and hammerhead nuts for mounting motor mounts and idlers
- 1 M3 x ? length screw - Length determined by motor chosen. Remove one screw from the nema17 motor housing and replace with longer screw for the rear motor stabilizer.
- 3 M5x25 BHCS - Z carriage to bed frame

<p align="left">
  <img src="images/Rear Motor Stab Screw.png" width="200">
</p>

Mathematical Potato Idlers:
- 2 M4x20 Socket head screws and hammerhead nuts
- 2 M5x40 Button head screws
- 2 M5 nuts
- 2 M5x15 Button Head Screws

DoubleT XYZ Idlers
 - Reuses existing fasteners for securing idler to Y extrusion
- 4 M3 heatset inserts
- 4 M3x30 Button head screws
- 2 M3x12 Socket head screws
- 2 M3x20 Socket head screws and hammerhead nuts
- 2 5mm x 25mm dowel
- 2 5mm x 20mm dowel
- 4 6mm x 3mm magnets



## Authors

* **genevamotion** - ** - [genevamotion](https://github.com/tdlane1) - *CAD design/ Modeling / Testing*
* **thiagolocatelli** - ** - [thiagolocatelli](https://github.com/thiagolocatelli) - *CAD design / Modeling / Project Management*

## Acknowledgements

* [MathematicalPotato](https://github.com/MathematicalPotato)
* [bythorsthunder](https://github.com/bythorsthunder)
* [Annex Engineering](https://github.com/Annex-Engineering)
* [Voron Design](https://github.com/VoronDesign)
* [Ramalama](https://github.com/Ramalama2)
* [clee](https://github.com/clee/VoronBFI)


## Images

<p align="center">
  <img src="images/genevamotion.jpg" width="800">
</p>

<p align="center">
  <img src="images/Frameless.png" width="800">
</p>

<p align="center">
  <img src="images/Side.png" width="800">
</p>


<p align="center">
  <img src="images/Bottom.png" width="800">
</p>


<p align="center">
  <img src="images/Bottom.png" width="800">
</p>


## Sample config (Manta M8P) - Economy Gearbox 

```
[stepper_z]
step_pin: ###
dir_pin: ###
enable_pin: ###
rotation_distance: 40
gear_ratio: 57:11   
microsteps: 32
endstop_pin: ###

##  Make sure to update below for your relevant driver (2208 or 2209)
[tmc2209 stepper_z]
uart_pin: ###
interpolate: False
run_current: 1.0
sense_resistor: 0.110
stealthchop_threshold: 0

```

# Builds

## Panzarkatten


<p align="center">
  <img src="images/panzarkatten.jpeg" width="800">
</p>


