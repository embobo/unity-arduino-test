# Unity Arduino Interfacing as an Input Controller

Provided are the requirements for Unity setup and interfaces for key components of the library

1. [Unity Settings for Serial Port](#serial-port-settings)
2. [Unity Settings for Arduino](#fitboard-arduino-settings)
3. [Fitboard Interace Methods](#fitboard-interface-methods)

## Setting Up Unity

### Serial Port Settings

Go to ***Unity** > **Edit** > **Project Settings** > **Player***

This will open a dialog in the Unity Inspector window. Under ***Optimization*** set ***API Compatibility Level*** to *.NET 2.0*

=

### Fitboard Arduino Settings

A prefab 'GameManager' will be provided in the asset bundle, it must be loaded in the main menu. It will not be destroyed on loading other scenes.

**FitboardDeviceInput.cs must be loaded before all other dependent Monobehavior scripts**

Go to *Edit /> Project Settings /> Script Execution Order*

In Inspector add FitboardDeviceInput.cs

Set time to at least -100 (or lower than lowest dependent script)

## Fitboard Interface Methods

Note that these are contained in 'DeviceKeyInputIF.cs' 

* `bool GetKeyDown (char key);` - return true if the key was pressed during this frame, otherwise false

* `bool GetKeyPressed (char key);` - return true if the key is currently pressed, otherwise false

* `bool GetKeyUp (char key);` - return true if the key was released during this frame, otherwise false
