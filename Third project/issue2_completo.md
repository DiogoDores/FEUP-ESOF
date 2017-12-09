# Issue T51739
This is a consistency issue on Blender's user interface. When using continuous grabbing, the cursor is hidden on edit mode, but visible on object mode. Used as visual assistance by some users, it still was confirmed as a bug.

In a similar fashion to T49451, besides being first reported 6 months ago, seemingly no progress had been made so we decided to have a take at it.

Click [here](https://developer.blender.org/T49451) for the original bug thread on Blender's official developer issues forum.

## Requirements
Below there are some instructions on how to replicate the issue:
1. Open Blender.
2. Select **Object Mode** on the 3D View bottom bar - should be on by default - and **create a new mesh** (i.e. a cube).
3. **Hold and drag** any mesh property with **slider input** (i.e. radius) and notice the **cursor stays visible** during the action.
4. Switch to **Edit Mode** on the 3D View bottom bar and repeat the process. The **cursor should be invisible** during the action.

![issue_2](https://github.com/DiogoDores/FEUP-ESOF/blob/master/Third%20project/issue2.png "Issue #2 Instructions")

## Source Code Files
This file can be found in the Blender folder under the directory `C:...\blender\source\blender\editors\interface\interface_handlers.c`. One single line of code was changed.

## Design of the fix
With the function ```ui_but_is_cursor_warp``` we were able to find whether the mouse was being used on a slider button or not. With the ```uiflag``` we were able to discover whether the mouse was visible or not.

![uml_2](https://github.com/DiogoDores/FEUP-ESOF/blob/master/Third%20project/uml_issue_2.png "UML")

## Fix source code
We found out this issue is related to the `USER_CONTINUOUS_MOUSE` macro which controls the warping of the mouse through the screen edges whilst dragging the cursor on a slider interface object.  
This macro's utilized on the `ui_but_is_cursor_warp` function which returns `true` if the user has selected the `Continuous Mouse` option present on Blender's `User Preferences`.  
This option, introduced on a recent patch, appears to break mouse hiding on sliders, so our solution ended up being returning `false` instead of `true` still maintaining the continuous mouse integration, yet enabling the cursor on every slider.

```cpp
if (U.uiflag & USER_CONTINUOUS_MOUSE) {
   if (ELEM(but->type,
       UI_BTYPE_NUM, UI_BTYPE_NUM_SLIDER, UI_BTYPE_HSVCIRCLE,
       UI_BTYPE_TRACK_PREVIEW, UI_BTYPE_HSVCUBE, UI_BTYPE_CURVE))
   {
       return false;
   }
}
``` 

## Submission
This issue should be handled by the User Interface team as the expected behavior is ambiguous. It isn't specified whether every slider bar must hide the cursor or leave it visible.  
The issue simply stated inconsistencies with the behavior and our solution makes the cursor visible on every slider, including sliders where the cursor would previously hide.  
Given the fact that this change might be unwelcome we ended up not submitting this solution.
