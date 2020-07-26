### Uwanted Parasitic BJTs



 - Modifications were made to the **SCN6M_SUBM.10.tech** File.
 - Modified Technology File:  **SCN6M_SUBM_modified.10.tech**
 
 Note: 
 **To ensure that the Vertical Parasitic PNP BJT was recognized and extracted correctly, the line below was added to the Technology File.**

```
 device bjt PNP nwell,nsc/a,nsd pdiff,pdc/a pwell,space/w,psc/a,psd 
```

However, this line seems to cause unwanted BJTs to appear in places where they are not there, even when only a partial requirement is met for the BJT.




### Magic Files

- **PNP.mag**
  seems to extract the BJT properly using the SCN6M_SUBM_modified.10.tech Technology File.
  
- **PMOS.mag**
  Post Extraction, using the SCN6M_SUBM_modified.10.tech Technology File, an unwanted BJT appears in the spice netlist.
  
  
  *********************************************************************************************************
  
 #### bandgap directory
  
 -**bandgap_no_bjt.mag**
 
  *Using SCN6M_SUBM.10.tech Technology File*
  ```
  %extract warn all
  %extract all
```
Select the shaded warning area.
  ```
  %feedback why
```
 Note: 
 1.Certain warnings regarding the node labels not being placed in the overlap area pop-up.
   ```
  %ext2sim
  %ext2spice
```
 Note: 
 2.The extracted Spice netlist seems normal, other than parasitics, no unwanted elements.
 
 
 **************************************
  
 
  *Using SCN6M_SUBM_modified.10.tech Technology File*
  ```
  %extract warn all
  %extract all
```
Select the shaded warning area.
  ```
  %feedback why
```
 Note: 
 1. Warnings regarding 1 device terminal missing pop-up (Magic is assuming that I forgot to add a BJT terminal and I want a BJT because of the way the device has been defined.)
 2. Certain warnings regarding the node labels not being placed in the overlap area pop-up.
 
   ```
  %ext2sim
  %ext2spice
```
 Note: 
 2.The extracted Spice netlist contains parasitics, and unwanted parasitic BJTs.
 
 
  #### Final Note

 
 1. All Simulation & Layout Files for the designed Bandgap Reference can be found [here](https://github.com/sherylcorina/avsdbgp_3v3).
 The Unwanted Parasitic BJTs didn't seem to affect the postlayout simulation of the Bandgap, only a few floating parastic capacitances were required to be deleted/commented to run the simulation.
 2. Please feel free to use the Modified Technology File, on your own circuits to see if the unwanted parasitic BJTs appear in the extracted Spice netlist and check if that affects your postlayout simulation.
 3. I will continue updating this repository with more circuits, to study the issue.
 4. If you find a fix or have suggestions to improve the modification, please create an issue or contact me.

 #### Contact Information

- Sheryl Serrao, Undergraduate Student, Mumbai University sherylcorina@gmail.com
