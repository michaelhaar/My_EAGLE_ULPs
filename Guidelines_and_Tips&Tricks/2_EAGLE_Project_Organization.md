# EAGLE Project Organization
We are using the following project structure for all our EAGLE projects:
```
christmas_tree_pcb/                         //project root directory
|-- christmas_tree_pcb_v02.brd              //latest EAGLE files
|-- christmas_tree_pcb_v02.sch              //latest EAGLE files
|-- 00_Archive/                             //old EAGLE files
|-- 10_Manufacturing/                       //manufactured PCBs
|   |-- V01/                                //version number
|   |   |-- 00_Archive/
|   |   |-- 10_Gerber/                      //submitted gerber files
|   |   |-- 20_BOM/                         //opt: bill of materials
|   |   |-- 30_Step/                        //opt: 3D step files
|   |   |-- 40_Pick&Place/                  //opt: files for the pick&place machine
|   |   |-- 50_Assembly/                    //opt: assembly drawings
|   |   |-- christmas_tree_pcb_v01.brd      //EAGLE files of version 01
|   |   |-- christmas_tree_pcb_v01.sch      //EAGLE files of version 01
|   |-- V02/
|   |   |-- 00_Archive/
|   |   |-- 10_Gerber/
|   |   |-- 20_BOM/
|   |   |-- 30_Step/
|   |   |-- 40_Pick&Place/
|   |   |-- 50_Assembly/
|   |   |-- christmas_tree_pcb_v02.brd
|   |   |-- christmas_tree_pcb_v02.sch
...
```

## Root directory
The root directory contains only the latest pcb versions

### Versioning
We are generally using the following versioning guidelines

-**Major version numbers** change whenever a new pcb is released for manufacturing
-**Minor version numbers** change when something is change in the EAGLE files, but
not yet released for manufacturing.

Version numbers are appended to the filename of the .sch and .brd file.
e.g.: 01v27 means major version 01, minor version 27.

## Archive
We copy the schematic and board file and increase the version if we want to
make changes to a PCB design. The old files are then moved into the archive.

## Manufacturing
This subfolder contains all manufactured PCB versions.

## V__ Folder
contains all available files for the manufactured PCB version.

## Gerber
contains the gerber files, which were submitted to our PCB supplier.

## BOM (optional)
Contains the bills of material for various assembly variants.
