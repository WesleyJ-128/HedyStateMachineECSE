<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->

## How it works

This is a hardware implementation of the statemachine used on FRC Team 95 Grasshopper's 2022 robot.  The game that robot played involved collecting and shooting colored balls, where only the correct color ball would score points.  Therefore, the statemachine handles indexing the balls correctly for shooting (the robot could store up to two) and sorting and ejecting the wrong-colored balls.  A detailed description of the statemachine is here: [ChiefDelphi build thread](https://www.chiefdelphi.com/t/frc95-2022-build-thread/398263/135), and a demonstration of the robot's sorting functionality is on [YouTube](https://www.youtube.com/watch?v=aGvHqtWoyaA).

## How to test

Referencing the diagram in the ChiefDelphi post, input 0 is S and input 1 is ST.  SP (the previous state of S) is handled internally.  Input 3 and input 4 provide color information-- when input 3 is low, color is NONE; when input 3 is high, color is Right if input 4 is high and Wrong if input 4 is low.  Outputs 0 through 4 represent the current state- only one is ever high at a time.  In order, they are: Idle, Indexing, Shooting, Eject_A, Eject_B.

## External hardware

None necessary to test, but theoretically this could be used as a custom circuit on the actual robot and replace the statemachine in code.
