# BACTERIOPHAGES

![bacteriophage reference](bacteriophage.png)

## SETUP

 * Blender version 4.0
 * Blender empty file

## WORKFLOW

- Delete the cube
- Activate Extra Objects and Curve Tools plugin for curves
- Go to front ortho view
- Add the reference `SHIFT-A` add image reference
- `GX` to move left
- Add a collection named Virus
- Add a Curve spiral archimedean
- Turns 21
- Steps 24
- Radius Growth 0.0
- Radius 0.12
- Height 0.06
- Go to Data - Geometry - Bevel and set depth to 0.035
- Add baseplate, a cylinder with 64 vertex, Radius .2 and depth .1. 
- Edit mode edge and select edge loops top and bottom `ALT-LMB` and the `CTRL-ALT-LMB`
- `CTRL-B` and Bevel increasing steps with mouse wheel
- Duplicate for collar
- Select top face of collar, extrude in place and scale, then extrude to make the 'neck'
- Add Head icosphere subdivisions 1 and Radius 0.5
- Join collar and head
- Select Sheath and `F3` convert to mesh
- Add simple deform modifier to the Sheath
- Set to Bend 0 degrees
- Select 3 top vertex in the middle line of coil and CTRL click Head, `CTRL-P` and make vertex parent
- Bend now
- Add Empty object to origin named it BendPivot
- Set as Origin for the bend modifier, now we can rotate the bend

- Hide the virus
- Create a curve point for the leg
- `CTRL-LMB` to add 2 more points
- Select mid point
- `N` Edit Fillet/Chamfer
- Data, Geometry Bevel 0.035
- Convert to mesh
- Select edgee loop at the end press `F` to close
- Extrude
- Scale 0
- On list of object press `M` to move Leg in Virus collection
- Add Armature
- Enter edit mode position top of bone in the middle of leg
- Extrude and put at end of leg BEFORE THE END SPIKE
- Back to object mode
- Select leg
- CTRL click armature
- CTRL-P parent leg to Armature with Automatic wights
- Set bones Object properties display as wire
- We now have a leg with a single control point
- Parent Sheath to SheatBEndPivot
- Parent Bend pivot to Baseplate
- Parent RiggedLeg to Baseplate
- Add emnpty sphere as control point and make parent
- Go on top view
- Pivot to 3D cursor on top
- Duplicate anb Rotate 45


NEW FILE: bacteriophage_animated.blend

- Delete all legs copies
- Animate the bend modifier angle with noise
- Animate the bend pivot rotation angle with noise
- Animate LEG and select frams `SHIFT-E` make cycle F-Modifier
- Duplicate the legs again (SELECT ALL!!)
- Shift the animations in timeline summary
- Add a path 5 m rotated 90 on Z
- Edit spline path
- Add constraint follow path to virus pivot
- Animate Path, you can see Evaluation Time modifier in Curve Animation sheet
- Make a plane and move up the Path 
- Render!


NEW FILE: COMPOSITING

## REFERENCES

 * https://www.youtube.com/watch?v=MQ4SKUZ2uGo
 

### COLORIZE

https://www.google.com/search?q=blender+transparent+glass&oq=blender+transparent+glass&gs_lcrp=EgZjaHJvbWUyCQgAEEUYORiABDIHCAEQABiABDIHCAIQABiABDIICAMQABgWGB4yCAgEEAAYFhgeMggIBRAAGBYYHjIICAYQABgWGB4yCAgHEAAYFhgeMgYICBBFGEDSAQg0ODg2ajBqMagCALACAA&sourceid=chrome&ie=UTF-8#kpvalbx=_zZZwZf31M8rxkgWZ3KqYDw_28