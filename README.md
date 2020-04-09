## LDTtool
(Version 1; 09/04/2020)
ArcGIS toolbox that implements the Landscape Dynamic Typology (LDT) method developed by Machado et al. 2018. The main purpose is to assess Land use / Land cover changes between two moments, considering a binary landscape composition and configuration.

It consists of two tools: 
"1 - Landscape Dynamic Types"; Implements the core LDT method. 
"2 - Forecast"; Calculates an hipothetical scenario for the future based on the assumption that the existing trends will persist. 

___

### How to use LDTtool

**Preliminary steps**
 
1. Create a File Geodatabase.
2. Make it the default Geodatabase (while creating it or after in: Menu File, Map Document Properties, Default Geodatabase (select).
3. Import the feature classes corresponding to the study area polygon, landscape moment 1 and landscape moment 2 into the Geodatabase.
4. Add the field “Area_ha” to both landscape feature classes and and calculate it. It should display the area in hectares.
5. Add the “LDTtool” toolbox to ArcToolbox.
6. Select the Geodatabase as “Current workspace” and “Scratch workspace in Geoprocessing menu, Environments, Workspace (select).
7. Select the Geodatabase as “Current workspace” and “Scratch workspace” in the Arctoolbox Environments; Workspace. (select).
8. Confirm the paths are correct within each tool (1 – Landscape dynamics types and 2 – Forecast) by Right-clicking; Properties; Environments; check the Workspace box, Values button.


**Inputs and settings**
 
Tool 1 – Landscape Dynamics Types:
- Study Area Polygon: Polygonal feature class containing the study area boundaries.
- Landscape Moment 1: Polygonal feature class of the landscape in moment 1 (earlier date).
- Landscape Moment 2: Polygonal feature class of the landscape in moment 2 (later date).
- Squares width and height (meters): Analytic square size.
- Keep patches equal or larger than (hectares): Minimum patch size to be analysed.
- Output Feature Class: Name and path of the output file.

Tool 2 - Forecast:
- Landscape to forecast (Output of tool 1)


**Output**

The final product is a feature class with the study area divided by squares, each one with the metrics calculated for both dates, their variation and assigned to a Type of Dynamic. 

___



 
References:
Machado, R., Godinho, S., Pirnat, J., Neves, N., Santos, P., 2018. Assessment of landscape composition and configuration via spatial metrics combination: conceptual framework proposal and method improvement. Landsc. Res. 43, 652–664. https://doi.org/10.1080/01426397.2017.1336757
