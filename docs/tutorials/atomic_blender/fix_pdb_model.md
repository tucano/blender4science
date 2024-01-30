---
layout: default
title: Fix a PDB Model
parent: Atomic Blender
nav_order: 2
---

## LOAD A PDB FILE

### Setup

 * Blender version 4.0
 * Blender empty file

### PDB MOLECULE

Got a structure of ciprofloxacin in SDF format from here: 

https://www.molinstincts.com/sdf-mol-file/ciprofloxacin-sdf-CT1000048109.html

translated to PDB with: 

https://datascience.unm.edu/tomcat/biocomp/convert (3D)

Sometimes you get DivisionByZero, try to use a different converter.

### WORKFLOW

1. Delete the cube with `X`
2. Import file [Ciprofloxacin](https://raw.githubusercontent.com/tucano/blender4science/main/course_material/Atomic_Blender/02_fix_pdb/ciprofloxacin.pdb)

3. Import Settings:

    | Parameter     | Value      |
    |:--------------|:-----------|
    | Balls type    | Mesh       |
    | Balls radius  | 0.5        |
    | Stick type    | Duplivert  |
    | Bonds         | Active     |
    | Bond radius   | 0.1        |

4. Now we are going to merge all atoms and sticks to create a unique mesh. We will work in the Outlier
5. Select Hydrogen and hide it, notice that the sticks are closed. 
6. Remove the cups just deleting the underling model (Hydrogen_sticks_cup)
7. Do the same for all sticks: extra faces will interfere with shading.
8. Convert the instance of Carbon_Stick_mesh to a real mesh: `CTRL-A` and make instance real.
9. Select an active stick with `CTRL-Click` and `CTRL-J` to join segments
10. `TAB` to enter edit mode and than `M` and merge by distance to cleanup vertices
11. Do this tedious thing for all the sticks, remember to go back in object mode.
12. Join all sticks in a single mesh: select in outlier and `CTRL-J` and rename it `sticks`
13. On Outlier, create a new collection under Scene collection (name: 'Molecule')
14. In Outlier move the sticks object to the new collection
15. Do the same with atoms:
    - `CTRL-A` make instance real
    - `CTRL-Click` and select one atom
    - `CTRL-J` and join all
    - `TAB` and `M` to merge by distance
16. Merge all atoms together with `CRTL-J`
17. Named it balls and move to the collection `Molecule`
18. Select balls: In the Material properties you notice there are multiple materials: rename them as XXX.Atoms (example: Carbon.Atoms)
19. Now we want to separate the bonds and atoms materials. Select sticks and make new materials called XXX.Bonds
20. We can now merge sticks and balls with `CTRL-J`
21. Rename final mesh `Ciprofloxacin`
22. Now that we have a single molecule we can do a lot of cool things! For example let's WAVE this molecule for no reason!
23. On Modifiers add a Wave modifier, play animation and see your molecule waving!
24. Add a rotating animation: 
    - Remove the wave
    - `N` for item properties
    - `I` overing 'Rotation' to insert a keyframe
    - Go to frame 100
    - Rotate 360 on Z axis with `RZ360`
    - Go to frame 120
    - Rotate again on Z axis 360
25. Render animation (EEVE)
