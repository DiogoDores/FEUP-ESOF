# Issue T49451
This issue was first noticed on the 25th of September of 2016. It has already been assigned to a user, but as no progress seemed to be made, we decided to try and solve it.

Briefly, what this issue caused was a reset in the unit values (meters, miles, etc.) after an object was created and one of its properties (i.e. radius, location, etc.) was altered.

Click [here](https://developer.blender.org/T49451) for the original bug thread on Blender's official developer issues forum.

## Requirements

Below there are some instructions on how to replicate the issue:

1. Open Blender
2. In the *Scene* tab, in the *Units* section, select any type of measurement unit in *Unit Presets* ![#c5f015](https://placehold.it/15/c5f015/000000?text=+) 
3. In the *Create* tab, create any type of object ![#f03c15](https://placehold.it/15/f03c15/000000?text=+)
4. In the object's options, change its size ![#1589F0](https://placehold.it/15/1589F0/000000?text=+)
5. The measurement unit that was previously selected has been reset to "None"

![issue_1_instr](https://github.com/DiogoDores/FEUP-ESOF/blob/master/Third%20project/cube_units.png "Issue #1 Instructions")
![bug](https://github.com/DiogoDores/FEUP-ESOF/blob/master/Third%20project/units_after.png "Demonstration of the bug")

## Source Code Files

In order to solve this issue, one file was changed and 14 lines of code were added. This file can be found in the Blender folder under the directory C:\...\blender\source\blender\blenkernel\intern\blendfile.c

We started by searching for the specific part of the code in which the scene was altered to its default settings. The first function discovered was ED_undo_step() in bf_editor_util/undo.c. By analyzing step by step each line of code we were able to climb down until `setup_app_data()` in blendfile.c, as mentioned previously. The functions analyzed were as follows: 
`BKE_undo_name()`, `BKE_undo_step()`, `read_undosave()`, `BKE_blendfile_read_from_memfile()`.

## Design of the Fix

With the function `CTX_wm_screen()` we were able to obtain blender's current screen, which contains the current scene, from where we can alter its Unit values (which itself is a UnitSettings struct).

![uml](https://github.com/DiogoDores/FEUP-ESOF/blob/master/Third%20project/uml_issue_1.png "UML")

## Fix Source Code

We discovered that the scene the user was currently using was stored in a struct with all its information. The variables that we were needed to analyse were being stored in a *UnitSettings* struct inside the main *Scene* struct. By tracking the values of the scene step by step carefully we were able to understand that the values were being reset to their default values, and all we needed to do was undo this operation, which sounds easier than it actually is. Thus, this issue was solved by instantiating a temporary variable holding the unit values before any changes were made and later assigning those values to the current scene. Here is the code altered in C:\...\blender\source\blender\blenkernel\intern\blendfile.c correctly documented.

```Cpp
/* Create temporary UnitSettings to use later (see issue T49451)*/
	UnitSettings temp_unit;
```

```Cpp
curscene = curscreen->scene;
/* Assigns the temporary unit to be equal to the current scene's unit, in order to hold in the values before everything is reset*/
temp_unit = curscene->unit;
```

```Cpp
/*The values of the current scene unit system have been reset. Therefore, we must fill them with the values previously saved previously*/
curscene->unit = temp_unit;
```

## Submission
The patch was pushed to the rB Blender repository and, as we speak, is awaiting approval.  
Its progress may be tracked on this [differencial link](https://developer.blender.org/D2953).

