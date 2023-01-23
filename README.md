# Voron Trident - Belted Z motion

This `mod` is the combination of multiple ideas for belted system for the Trident Z motion. Most of the inspitarion came from X0, which uses Nema 17 gearboxes. The main goal was to use 9mm belts for Z motion while keeping most of the original Trident skirts and not relocating Z steppers to the top of the printer. We give credit to `bythorsthunder` for his [Orion belted mod](https://github.com/bythorsthunder/Orion-Tri-Belt), which has also been proven efficient and easy to assemble (the same applies to the [belted z motion](https://github.com/MathematicalPotato/Voron_Mods/tree/main/VT_Belted_Z) mod introduced by `MathematicalPotato`).

Created/Elaborated/Modified by `DoubleT` and `Genevamotion`

Disclaimer: This is *not* a official Voron mod/design.

## BOM

- 3 Nema 17 with gearbox
	- [Ali Express](https://www.aliexpress.us/item/3256804434852612.html)
	- [Amazon](https://www.amazon.com/STEPPERONLINE-Planetary-Gearbox-Stepper-Printer/dp/B00WATUFIG)
- 9mm GT2 belts
- 3 9mm 20T GT2 drive pulleys, 8mm ID
- 3 9mm 20T toothed idlers, 5mm ID (F695 Bearings and shims can be used as well)
- 9 M3x12 Button head screws (mounting gearmotors)
- 7 M3 heatset inserts
- 4 M3x30 screws (front motor mount bracing)
- 3 M3x35 screws (belt tensioners)
- 2 M5x35 screws and nuts (front idlers)
- 1 M5x25 screw and nut (rear idler)
- 8 M5x10 screws and hammerhead nuts (mounting motor skirts)


## Images

<p align="center">
  <img src="images/genevamotion.png" width="800">
</p>

<p align="center">
  <img src="images/image1.png" width="800">
</p>

<p align="center">
  <img src="images/image2.png" width="800">
</p>


<p align="center">
  <img src="images/image3.png" width="800">
</p>


<p align="center">
  <img src="images/image4.png" width="800">
</p>


## Sample config (Manta M8P) 

```
#####################################################################
#   Z Stepper Settings
#####################################################################

##  Z0 Stepper - Front Left
##  Connected to MOTOR_3
##  Endstop connected to M3-STOP
[stepper_z]
step_pin: PD7
dir_pin: !PD6
enable_pin: !PF10
# Rotation Distance for TR8x8 = 8, TR8x4 = 4, TR8x2 = 2
rotation_distance: 7.75    
microsteps: 32
endstop_pin: PF5
##  Z-position of nozzle (in mm) to z-endstop trigger point relative to print surface (Z0)
##  (+) value = endstop above Z0, (-) value = endstop below
##  Increasing position_endstop brings nozzle closer to the bed
##  After you run Z_ENDSTOP_CALIBRATE, position_endstop will be stored at the very end of your config
#position_endstop: -0.5
## All builds use same Max Z
position_max: 250
position_min: -2.5
homing_speed: 8.0 # Leadscrews are slower than 2.4, 10 is a recommended max.
second_homing_speed: 3
homing_retract_dist: 3

##  Make sure to update below for your relevant driver (2208 or 2209)
[tmc2209 stepper_z]
uart_pin: PF9
interpolate: False
run_current: 1.0
sense_resistor: 0.110
stealthchop_threshold: 0

```