---
layout: default
title: Bacteriophage
parent: Blender Workflows
nav_order: 1
---

## BACTERIOPHAGE

Let's create a low poly model of a Bacteriophage.

Reference: 

![bacteriophage reference](../../assets/images/bacteriophage.png)


### Setup

 * Blender version 4.0
 * Blender empty file

### Workflow

1. Delete the cube with `X`
2. In `Edit` --> `Preferences` --> `Add-ons` Activate Extra Objects and Curve Tools plugin for curves 

    ![addons](../../assets/images/Curve_and_Extra_tools.PNG)

3. Go to front orthographic view with `NumPad 1` or using the [Navigation Gizmo](https://docs.blender.org/manual/en/latest/editors/3dview/navigate/introduction.html#navigation-gizmo) 

    ![Navigation Gizmo](../../assets/images/navigation_gizmo.png)

4. Add the reference: `SHIFT-A` add image reference `bacteriophage.png`
5. `GX` to move reference to the left
6. In the Outliner, Right mouse button (`RMB`) and add a collection named Virus

    ![Blender UI](../../assets/images/Blender-Interface-1200.jpg)

7. Add a Curve spiral archimedean

    ![bacteriophage sprial](../../assets/images/bacteriophage_spiral_parameters.png)

    | Parameter     | Value      |
    |:--------------|:-----------|
    | Turns         | 21         |
    | Steps         | 24         |
    | Radius Growth | 0.0        |
    | Radius        | 0.12       |
    | Height        | 0.06       |

8. In `Properties` --> `Data` --> `Geometry` --> `Bevel`, set depth to `0.035`
9. Add the baseplate, a cylinder with `64` vertex, Radius `.2` and depth `.1`.
10. Edit mode with `TAB` and press `2` for edge select
11. Select edge loops top and bottom `ALT-LMB` and `SHIFT-ALT-LMB`
12. `CTRL-B` and Bevel increasing steps with mouse wheel
13. Duplicate for collar with `SHIFT-D`
14. `GZ` to grab and move up collar
    
    ![bacteriophage body](../../assets/images/bacteriophage_body.png)    

15. Edit mode with `TAB` and press `3` for face select
16. Select top face of collar, extrude with `E` in place and scale, then extrude again to make the 'neck'
17. With top face of neck selected: `SHIFT-S` and `2` for cursor to selected
18. Object Mode with `TAB`
19. Add Head icosphere with `SHIFT-A` subdivisions `1` and Radius `0.5`
20. Move Head up with `GZ`

    ![bacteriophage body](../../assets/images/bacteriophage_body_and_head.png)    

21. 