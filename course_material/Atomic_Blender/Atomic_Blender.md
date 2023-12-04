# Loading protein pdb-files into Blender

## Setup

 * Blender version 4.0
 * Blender file: `01_load_pdb.blend`

## Install addons

Go to Edit/Preferences --> Add-ons 

Install Atomic Blender PDB/XYZ

## Import pdb file

shortcut `X` and delete the cube.

Menu File --> Import --> PDB file

Import morphine.pdb

## Play with model and make a render

Outliner morphine.pdb to select atoms and stics

Play with Hide in viewport and/or in renders

Change the camera position selecting it in outliner

Toggle camera View (Numpad 0 or Button top right in layout)

`GZZ` or other axis to move the camera

`F12` or render view to make a nice photo

Atmoic Blender Utilities in Create menu on top right (undeer tools) `N` key to toggle

Reference is ![Morphine Image from Wikipedia](Morphine_molecule_ball.png)

On Utility Panel:

set Carbon, Oxygen and Nitrogen spheres radius in pm to 40.0

## Change materials

Change atoms colors from material panel.

All atoms: .25 metallic .25 rough

## Add a plane

Camera view Numpad 0

`SHIFT-A` add plane mesh

Select camera, select plane with `SHIFT` hold

Press `N` Item panel Z rotation, right click copy single to selected to algin plane to camera

Grab and move down, scale

Edit mode, edge mode, select far edge `EZ` extrude on Z axis

Select middle edge

`CTRL-B` to bevel, move mouse, mouse wheel to increse segmentation

APPLY SCALE! `CTRL-A`

Test Render

Remove shadows on Light object


## Fix PDB model

Working file file `02_fix_pdb.blend`

Got a structure of ciprofloxacin in SDF format from here: https://www.molinstincts.com/sdf-mol-file/ciprofloxacin-sdf-CT1000048109.html

translated to PDB with: 

https://datascience.unm.edu/tomcat/biocomp/convert (3D)

Sometimes you get DivisionByZero, try to use a different converter.


IMPORT SETTINGS

 * BALLS AS MESH with Balls radio 0.5
 * Sticks DUPLIVERT with Bonds and 0.1 Radius


Now we are going to merge all atoms and sticks, because the collection model is painful in some cases, especially if you and more than 1 molecule.

1. Delete all the cups `X` and check result, all sticks are open now. We can now link meshes with join and extra faces and the top will interfere with shading.

2. Now take Carbon_Stick_mesh and `CTRL-A` and make instance real.

3. Now hold `SHIFT` select again a segment that became active.

3. `CTRL-J` and join and delete the old instances with delete hyerachy

4. `TAB` to enter edit mode and than `M` and merge by distance

Do this tedious thing for all the sticks, remember to go back in object mode.

Join all sticks in a single mesh
Rename to bonds and move to another collection

Do the same with atoms

 - `CTRL-A` make instance real
 - `SHIFT` and select one atom
 - `CTRL-J` and join all
 
Select materials for Atoms and rename it as XXX.Atoms and duplicate XXX.Bounds

Now that each part has his material let's merge with `CTRL-J`

Now that we have a single mesh we can apply modifiers!!!!

Add a wave for example and press play.

Remove wave

Animation:

`I` to insert rotation keyframe,

go at fram 100, select object molecule and rotate 360 with `RZ360` and left click

`I` to insert another keyframe

PLAY

Add a second fast rotation 20 framse from 100 to 120

Go to output panel set frames to 150, set format to FFmpeg video

REnder animation from menu (or `CTRL-F12`)











## References

 * [Luminous Lab - Import pdf files](https://www.youtube.com/watch?v=3nCeQErv8Fg)
 * http://www.malte-reimold.de/blender/pdb2blend.html
 * [Low poly planet tutorial - Background Plane](https://www.youtube.com/watch?v=8FXJJDFAL6o)
 * [BLENDER for SCIENCE - ANY MOLECULE](https://www.youtube.com/watch?v=zXJKYvuCPYY)

