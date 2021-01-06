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
  
  Find //extrude mintemp on line 325 and change the value to 140.\
  Now upload this firmware to the Prusai3 via Arduino and it should override the minimum temperature for Prusai3 extruder.
  
  You can also find the modified [Configuration_prusa_Modit.h](Configuration_prusa_Modit.h) in this Github repository
  
  For 3D printing multimateiral using single extruder. We followed the article by rainerwp: [Prusa i3 MK3: Real Multicolour prints without MMU](http://schlosshan.eu/blog/2019/03/02/prusa-i3-mk3-real-multicolour-prints-without-mmu/)\
  
  While the print setting may vary depending on the machine and the quality of assembly, the summary of the print settings we used in the TCB paper is as below:
  
| --|Temperature | Speed | infill | Extrusion multiplier | 
| ---|--|--|--|--|
| Conductive PLA | 150°C  | 10mm/s | 99% |1.1|
| White PLA | 205°C. | 35mm/s | 99% | 1.0|

We recommend 2 layes for single sided TCB and 4 layers for double-sided TCB\
For constucting TCB with thicker substrates, we recommend increasing the layer height instead of layer numbers.\
For double sided TCB it requrie 4 switching between PLA and condcutive PLA in order below. \
PLA > conductivw PLA > PLA > Conductive PLA > PLA

Conductive PLA leaves larger amount of residue in the nozzle, so ensure when switching from conductive PLA to normal PLA that visually no residue is apparant.

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

PLA has inherently low glass transitional temperature 55 to 60 °C which means and can be easily thermoformed using accessible heating equipments.\
Once the PLA is heated to the glass transitional state, it should feel rubbery and can be bent to the desireable shape.\
We used desktop hot-air blower station with the small tip to heat the target region accurately.

Once bent the PLA should cool down and sets into the new shape in room temperature within a minutes.



---
4. Component Assembly

To attach electrical component onto TCB, we used a conductive silver ink curable at a room temperature.\
Conductive silver ink takes up to 12 hours to fully cure at a room temperature, but within 20min the applied surface becomes touch dry.\
The silver ink has a weak adhesive propoerties, so we applied a layer of superglue on top of the coated TCB trace and the lead of the electrical component to enhance the adhesive strength. We noticed that this does not interfere with the conductivity of the applied silver ink.

It is also possible to use conductive silver epoxy, which has greater adhesives propoerties. However, it takes much longer to cure so we used the conductive silver ink with the super glue instead.

For connecting lead of microcontrolelr to the sockets, we recommend sharpeneing the tip of the arduino pins for easier insertion into the sockets.\
Simply push the sharpned pins into the socket and apply silver ink to reduce the contact resistancy.


