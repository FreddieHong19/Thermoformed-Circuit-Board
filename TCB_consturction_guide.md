**TCB Consturction Guide**

TCB can be constructed with commonly found materials.

The list of the suppliers can be found in the [mateirals and suppliers](Material_and_Supplier.md) section.

---
1. 3D Printing Conductive PLA with Prusai3


  The recommended printing temperature of the Conductive PLA (*Electrifi*) is between 140-160°C.
  In our experiment we found that 140°C is too low for consistent extrusion quality on Prusa i3.
  We found that 150°C outputs a good printing quality and reistance. 
  
  By default Prusai3's firmware allow minimum printing temperature of 180°C.
  So in order to use *Electrifi*, the firmware file need to be edited.
 
  To Edit the Prusa Firmware:/
  Firstly, download the editable firmware file from [Prusa3D GitHub Pages](https://github.com/prusa3d/Prusa-Firmware)\
  Open **configuration_prusa.h** found in *Prusa i3 configs\Prusa-Firmware-3.8.1\Firmware\variants*.
  
  Find //extrude mintemp on line 325 and change the value to 140./
  Now upload this firmware to the Prusai3 via Arduino and it should override the minimum temperature for Prusai3 extruder.
  

  For 3D printing multimateiral using single extruder. We followed the article by rainerwp: [Prusa i3 MK3: Real Multicolour prints without MMU](http://schlosshan.eu/blog/2019/03/02/prusa-i3-mk3-real-multicolour-prints-without-mmu/)\
  
  
---
2. Copper Electroplating


We used commonly found copper electroplating kit online to formulate the copper electrolyte.

1L of Copper plating electrolyte solution consists of: \
-Diluted Sulphuric Acid. \
-Copper Sulphate crystals \
-Distilled Water \
-Additive Brigtner (optional) 

Please wear appropriate PPE before formulating the plating bath.

First, prepare luke warm distilled water in the plating tank, then add copper sulphate crystals into the tank.
Stir the tank until the copper sulphate is fully dissolved. We recommend preparing the solution on magnetic stirrer.
Slowly add the diluted Sulphuric Acid into the tank.
Add additive Brightner into the tank.

For Electroplating printed condcutive PLA we recommend supplying current using Voltage constant settings.
For TCB: We useD a drop of silver ink to minimise the contact resistance between the printed trace and the crocodile clips connected to the power supply. For larger circuits, we used multiple crocodile clips to distribute the current flow. We began electroplating at constant **low voltage (~0.2V)** until we observed that copper formed across the length of the circuit (~20min). As more copper deposited, we were able to increase current flow at constant voltage, increasing to **0.3V** then to **0.4V** (~40min). This reduces the amount of current otherwise forced through the PLA, which may lead to joule heating and deformation. Also, the bath was agitated with a magnetic stirrer at **400** rpm for homogeneous deposition following the electrodeposition guideline.

---
3. Thermoforming 

---
4. Component Assembly

