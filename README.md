# Klipper configuration for the FlashForge Creator Pro

This repository contains the Klipper configuration as I use for the FlashForge Creator Pro.  
Feel free to use this in any way you see fit, just keep in mind I cannot be held resposible for anything happening to your hardware, well-being or anything else.  

## How to add this configuration to your Klipper setup

1. Download the files by either:
  - doing a `git clone` of this repository on your device running Klipper in the `~/klipper_config` directory
  - doing a `git clone` of this repository on your local device, creating a `klipper-flashforge-creatorpro` directory on your Klipper device in the `~/klipper_config`, and uploading the files to just created diretory
  - downloading the `.zip` from GitHub from the `Code` -> `Download ZIP` button, unpack the files, creating a `klipper-flashforge-creatorpro` directory on your Klipper device in the `~/klipper_config`, and uploading the files to just created diretory
  - adding this repository as a submodule to your personal git repo of your Klipper config files
2. Load the files into your existing `printer.cfg` by adding these lines at the start of the file:
  ```
    [include klipper-flashforge-creatorpro/creatorpro.cfg]
    [include klipper-flashforge-creatorpro/creatorpro-macros.cfg]
   ```

## Add GCode to your slicer

In SuperSlicer for example go to `Printer Settings`, turn _on_ `Expert` mode and open `Custom G-code`.

For `Start G-code` set:
  ```
  T[current_extruder]
  START_PRINT BED_TEMP=[bed_temperature] EXTRUDER_TEMP=[first_layer_temperature]
  ```

For `End G-code` set:
  ```
  END_PRINT
  ```

For `Tool change G-code` set:
  ```
  T[next_extruder]
  ```

Other slicers may call these settings differently and may use different placeholders.
