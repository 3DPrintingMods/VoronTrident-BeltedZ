## BeltedZ components for Monolith Gantry

These parts were created for compatibility with [Monolith Gantry](https://github.com/CloakedWayne/Monolith_Gantry_V2-VT).  No changes are needed to the monolith gantry components. The mod includes modified Z idlers and *optional* Z carriages that relocate the bed 10mm in the +Y direction.  

The Notes and BOM differences may leave out critical information. These BOM differences are in relation to the BeltedZ mod, and not stock Voron components.  Apologies in advance if items were left out.

I'm lazy - Printing orientation has not been preset on many parts, but it's fairly obvious in most cases which side is down.

## Idler Notes

 - The front Z idlers currently use M5x45 screws as shafts for the idler pulleys to ride on.  This isn't a perfect solution, and a dowel-pin version is on the horizon.
 - The front Z linear guides will obstruct insertion and removal of the front-most fasteners that secure the idlers to the Y extrusions.  It is recommended that you install the front XY and Z idler assemblies **before** the Y linear guides.  This will allow the idler assembly to be slid along the Y extrusion for access to insert the fastener, and slid back into place for before final tightening of the fasteners.  Alternatively, you can remove the Z linear guide for access, but in most cases you will already have the Y linear guides removed during conversion to Monolith Gantry.
 - The rear Z idler has notches for the Monolith AB tensioners to clear, as well as provide access to the tensioning screws. These notches aren't needed in 250+ builds, but with Tiny-T they are necessary.
 - AWD idler spacers are provided.  These are needed to space the Z idler lower so that it can clear the shear support plates of the front motor mounts. Longer fasteners are needed to secure the idlers to the Y extrusions.
 - You may notice the front Z idlers have a circular relief in the top side that goes nowhere. This is to provide clearance for a fastener that may be present on the monolith front motorless mounts. BHCS is assumed in this case, and the fastener may need to be changed to fit the relief.

**Idler BOM Differences**

 - Idlers (2WD):
	 - 4x M5x16 
	 - 2X M5x20
	 - 2X M5x45

- Idlers (AWD):
	- 6x M5x20
	- 2X M5x45

## Bed +10 Notes
*Why relocate the bed?* - This isn't necessary, but some toolhead designs will place the hotend nozzle as close to the X axis linear rail carriage as possible to improve balance and center of mass. The front edge of the bed may be out of reach with stock carriages in this scenario.

 - A modified Z_Bed_Rear model is provided.  This part needs to be printed, as the stock Voron rear bed extrusion attachement interferes with the belt.  It has clearance for the belt as well as relocated fasteners that secure the spherical bearing to the part.
 - Z carriages elevate the bed 5mm over stock to reach PFA style toolheads on Tiny-T.  Verify total Z travel distance after completion as the new carriages have probably affected it.

**Z Carriage BOM Differences**

 - 4x M3x20
- 8x M3x25
- 3x M5x25

## Acknowledgements:

 - The BeltedZ mod was heavily inspired by MathematicalPotato's [VT_Belted_Z](https://github.com/MathematicalPotato/Voron_Mods/tree/main/VT_Belted_Z) mod
 - [CloakedWayne](https://github.com/CloakedWayne) - Monolith Gantry
