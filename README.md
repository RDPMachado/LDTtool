## LDTtool
(Version 1; 08/08/2020)
Name: LDTtool
License: GNU GPLv3
Developer: Rui Machado
E-mail: rdpm@uevora.pt
Accessiblehttps://github.com/RDPMachado/LDTtool
Year first available: 2020
Software required: ESRI® ArcMap™ 10.0 and later versions
Program language: Python
Program size: 6.96Mb

### Contents
"README.md" (this file, with details, descriptions and instructions)
"COPYING.txt" (License file)
"LDTtool.tbx" (toolbox)
"LDTsymbology2M.lyr" (Layer file with symbology for output file in two moments analysis. Field to apply: ToD) 
"LDTsymbology3M.lyr" (Layer file with symbology for output file in three moments analysis. Field to apply: ToD1_3)


### Description
ArcGIS toolbox that implements the Landscape Dynamic Typology (LDT) method developed by Machado et al. 2018. The main purpose is to assess land use / land cover changes between two or three moments, considering the composition and configuration of a binary landscape.

It consists of five tools: 

"1.1. Landscape Dynamic Types 2M (Squares)"; Implements the core LDT method using two moments and squares as analytical units. 

"1.2. Landscape Dynamic Types 3M (Squares)"; Implements the core LDT method using three moments and squares as analytical units.  

"1.3. Landscape Dynamic Types 2M (Districts)"; Implements the core LDT method using two moments and distrits provided by the user as analytical units.

"1.4. Landscape Dynamic Types 3M (Districts)"
Implements the core LDT method using three moments and districts provided by the user as analytical units.

"2 - Forecast"; Calculates an hipothetical scenario for the future based on the assumption that the existing trends will persist. 


___

### How to use LDTtool
**Preliminary steps**
 
1. Create a File Geodatabase.
2. Make it the default Geodatabase (while creating it or after in: Menu File, Map Document Properties, Default Geodatabase (select).
3.	Import the feature classes into the Geodatabase. The feature classes should be the landscape moment 1, landscape moment 2 and landscape moment 3 (optional). Regarding the analytical units, the feature classes are the study area boundary (for squares) or districts.
4. Add the “LDTtool” toolbox to ArcToolbox.
5. Select the Geodatabase as “Current workspace” and “Scratch workspace in Geoprocessing menu, Environments, Workspace (select).
6. Select the Geodatabase as “Current workspace” and “Scratch workspace” in the Arctoolbox Environments; Workspace. (select).
7. Confirm the paths are correct within each tool (1 – Landscape dynamics types and 2 – Forecast) by Right-clicking; Properties; Environments; check the Workspace box, Values button.

**Inputs and settings**

Tool 1 – Landscape Dynamics Types
- Study Area Polygon: Polygonal feature class containing the study area boundaries.
- Districts: Polygonal feature class containing the districts boundaries.
- Landscape Moment 1: Polygonal feature class of the landscape in moment 1.
- Landscape Moment 2: Polygonal feature class of the landscape in moment 2.
- Landscape Moment 3: Polygonal feature class of the landscape in moment 3.
- Squares width and height (meters): Analytic square size.
- Keep patches equal or larger than (square meters): Minimum patch size to be analysed.
- Output Feature Class: Name and path of the output file.

Tool 2 - Forecast
- Landscape to forecast (Output of tool 1)


**Output**

The final product is a feature class with the metrics calculated for the two or three dates and the districts or squares assigned to a Type of Dynamic.

___



 
References:
Machado, R., Godinho, S., Pirnat, J., Neves, N., Santos, P., 2018. Assessment of landscape composition and configuration via spatial metrics combination: conceptual framework proposal and method improvement. Landsc. Res. 43, 652–664. https://doi.org/10.1080/01426397.2017.1336757
