# Issue Report

For this project we were assigned to solve two different issues from the open-source 3D computer graphics software <a href="https://www.blender.org/">Blender</a>.

## Introduction

As none of the members in our group was accustomed to using this software, we attempted to solve issues related to the program's User Interface. This decision was made due to the fact that these issues were the most accessible in terms of replicating the error without prior knowledge of the software's usage.

## Issue #1 - T49451

##### <a href="https://developer.blender.org/T49451"> Units parameter resets to previous value </a>

This issue was first noticed on the 25th of September of 2016. It has already been assigned to a user, but as no progress seemed to be made, we decided to try and solve it.

Briefly, what this issue caused was a reset in the unit values (meters, miles, etc.) after an object was created and one of its properties (i.e. radius, location, etc.) was altered.

#### Requirements

Below there are some instructions on how to replicate the issue:

1. Open Blender
2. In the *Scene* tab, in the *Units* section, select any type of measurment unit in *Unit Presets* ![#c5f015](https://placehold.it/15/c5f015/000000?text=+) 
3. In the *Create* tab, create any type of object ![#f03c15](https://placehold.it/15/f03c15/000000?text=+)
4. In the object's options, change its size ![#1589F0](https://placehold.it/15/1589F0/000000?text=+)
5. The measurment unit that was previously selected has been reset to "None"

![issue_1_instr](https://github.com/DiogoDores/FEUP-ESOF/blob/master/Third%20project/cube_units.png "Issue #1 Instructions")

### Strategy
In order to solve this, we first thought of searching in the code for the interface listener where the object's properties were being changed. We've identified that in the *bf_windowmanager* project folder, in the *wm_operators.c* class, 

## Issue #2 - T51739
##### <a href="https://developer.blender.org/T51739"> Float slider in UNDO bug </a>

This is a consistency issue on Blender's user interface. When using continuous grabbing, the cursor is hidden on edit mode, but visible on object mode. Used as visual assistance by some users, it still was confirmed as a bug.

In a similar fashion to T49451, besides being first reported 6 months ago, seemingly no progress had been made so we decided to have a take at it.

### Strategy
It is imperial to find both the macros associated with each conflicting mode and the mouse visibility actuators. OB_MODE_OBJECT and OB_MODE_EDIT identify whether a given object is in object mode or edit mode, respectively. The ACT_MOUSE_VISIBILITY flag which is applied to a RNA interface element controls whether the mouse is visible or not while interacting with it.

## Conclusion

As we began these tasks we faced three main problems. Our first one was our lack of experience using this software, as it used a considerable amount of program specific terms and technical know-how we did not possess. Secondly, as this project was not based in Github, we had some dilemmas whilst trying to build it. Finally, and quite possibly the most debilitating problem, was the scale of this project, as it was already well developed. Obviously, it is also the goal of this course to aid us through this process and we believe we've mangaged to overcome most of the issues presented in the beginning.
