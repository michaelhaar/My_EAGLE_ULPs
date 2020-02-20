# Basic PCB Design Workflow

We usually use the following workflow for creating new PCBs:

## 1. Create a Project Folder
The first thing we do when we are designing a new PCB, is to create a new project folder/directory with the following structure:

```
christmas_tree_pcb/
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

## 2. Generate EAGLE files
Open EAGLE. Create a new *schematic* file as well as a new *board* file. Save them into the project directory as illustrated above. I also recommend using a new *library* file for all your projects. The goal is to use only parts from this project related library.

## 3. Draw the Schematic
We usually start with adding a frame to the schematic and just drawing the circuit.

## 4. Adding Components to the Library
In some cases there isn't any EAGLE footprint available for the selected part and you have to create it by yourself. Normally this step is done concurrently with step 3.
A more detailed tutorial on how to create good library parts can be found here.

## 5. Routing the Board
Routing the board is generally the most exhausting part in a PCB design. We recommend the following workflow:

### 5.1 Layer Stack and Supplier
Think about the layer stack and the PCB supplier that will be used. This will give you a rough idea of the dimensions and the design rules that should be applied.

We usually order our PCB's from [PCBWay](https://www.pcbway.com/), which is focused on PCB prototyping and low quantities. Cost for 10pcs of 100x100mm PCBs is approximately 5$+21$ shipping. Delivery time to our front door is usually less than one week.

### 5.2 Outlines and Component Placement
Define the dimension of the PCB using layer 20 and do a first draft of the part placement.

### 5.3 Routing and Finetuning
Once we got an idea of the component placement, we can start routing the traces and finetuning the position of the parts.

### 5.4 DRC and Gerber File Generation
It's crucial to double check your design before you release it for production. I recommend checking the schematic first, next the board, than **running a DRC** (design rule check) and finally generating your Gerber files.

Recommended Tools for viewing gerber files:
- [Tracespace](https://tracespace.io/view/) is probably the best Gerber viewer on the internet. I also use this tool for confidential projects, since it's just client based. Check out the [privacy policy](https://github.com/tracespace/tracespace/blob/v4.2.0/PRIVACY.md) for more information
- I would recommend [gerbv](https://sourceforge.net/projects/gerbv/) if you really need an offline solution.

### 5.5 Optional: 3D Model Generation
Sometimes you need the generate a 3D model of a PCB in order to see if it will fit into the available packaging space.
There are lot's of detailed tutorial on the internet. (Just google: "EAGLE export to Fusion")

### 5.6 Optional: Bill of Material (BOM)
The BOM is a list of all the components on the PCB, which can be created which an ULP (User Language Program) in EAGLE. This is useful for ordering the right amount of components or estimation the total cost of the PCB.
I've written a tutorial for this topic, which can be found here.

### 5.7 Optional: Assembly Drawings
The assembly drawing tells your manufacturer where the parts should be placed on the manufactured PCB.
A detailed tutorial on how to create a good assembly drawing can be found here.
