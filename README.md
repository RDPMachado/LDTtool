## LDTtool
(Version 2; 20/07/2022)
Name: LDTtool
License: GNU GPLv3
Developer: Rui Machado
E-mail: rdpm@uevora.pt
Accessiblehttps://github.com/RDPMachado/LDTtool
Year first available: 2022 (V1.0 in 2020)
Software required: ESRI® ArcMap™ 10.0 and later versions
Program language: Python
Program size: 18.5Mb

### Contents
"README.md" (this file, with details, descriptions and instructions)
"COPYING.txt" (License file)
"LDTtool_V2.0.tbx" (toolbox)
"LDTsymbology2M.lyr" (Layer file with symbology for output file in two moments analysis. Field to apply: ToD) 
"LDTsymbology3M.lyr" (Layer file with symbology for output file in three moments analysis. Field to apply: ToD1_3)


### Description
ArcGIS toolbox that implements the Landscape Dynamic Typology (LDT) method developed by Machado et al. 2018. The main purpose is to assess land use / land cover changes between two or three moments, considering the composition and configuration of a binary landscape.

It consists of four main tools:

Tool 1 – 'Landscape Dynamic Types' is composed by eight scripts and runs the core LDT steps to calculate the ToD. Those whose name contains ‘2M’ perform analysis between two analytical moments and those whose name contains ‘3M’ do so for three analytical moments. The suffixes ‘Squares’ and ‘Districts’ indicate the AU will be automatically generated squares or user-provided boundaries. For each of these tools there is a similar one which only difference is that it searches for the ToD ‘perforation’ inside the AU. This is optional and not standard because when it is assigned to an AU, it means that it occurred but does not mean it was the only area loss that occurred, so extra caution is needed to avoid misinterpreting the results. This is not a problem when the same procedure is applied to the entire LULC class, using the tool for perforation calculation, mentioned below.

Tool 2 – 'Forecast’ calculates a hypothetical scenario assuming the ongoing trends will persist. The forecast tool considers how the ToD can evolve from one to the other (Machado et al. 2018).

Tool 3 – 'Perforation’ is an accessory tool to geoprocess, at the class scale, the spatial pattern ‘Perforation’. It shows where perforation happened between two analytical moments.

Tool 4 – 'Gained and lost patches’ is an accessory tool to identify and locate the places where amounts of the LULC category of interest were gained and lost between two analytical moments, including new individual patches or individual patches that disappeared. It produces four output feature classes: all gains, gained patches, all losses and lost patches.

___

### How to use LDTtool
 
Relevant recommendations to prevent errors or malfunctioning are:

1) to use the same Coordinate Reference System (CRS) in the data frame and all the input elements;
2) to use Feature classes instead of shapefiles;
3) delete unnecessary attribute fields. The landscape FC must contain only one class with the polygons representing the object under study (habitat, biotope, LULC category, etc.).


The following preliminary steps are essential to ensure the toolbox correct functioning:

1. Create a File Geodatabase.
2. Select it as the default geodatabase.
3. Import the FC/shapefiles into the geodatabase. The FC should be the landscape moment 1, landscape moment 2 and landscape moment 3 (optional). Regarding the analytical units, the FC are districts or the study area boundary (for automatic square generation).
4. Add the LDTtool toolbox to ArcToolbox.
5. Select the Geodatabase as “Current workspace” and “Scratch workspace” in Geoprocessing menu, Environments, Workspace.
6. Select the Geodatabase as “Current workspace” and “Scratch workspace” in the ArcToolbox Environments, Workspace.
7. Confirm the paths are correct within each tool by Right-clicking; Properties; Environments; check the Workspace box, Values button.


The inputs and settings required to run the tools are the following:

Tool 1 – Landscape Dynamics Types
• Study Area Polygon: Polygonal FC containing the study area boundaries.
• Districts: Polygonal FC containing the districts’ boundaries.
• Landscape Moment 1: Polygonal FC of the landscape in moment 1.
• Landscape Moment 2: Polygonal FC of the landscape in moment 2.
• Landscape Moment 3: Polygonal FC of the landscape in moment 3.
• Squares width and height (meters): Analytic square size.
• Keep patches equal or larger than (square meters): Minimum patch size to be analysed.
• Output Feature Class: Name and path of the output file.

Tool 2 – Forecast
• Landscape to forecast (Output of tool 1)

Tool 3 – Perforation
• Landscape Before: Polygonal FC of the landscape in the earliest moment of analysis.
• Landscape After: Polygonal FC of the landscape in the latest moment of analysis.
• Perforation Output Feature Class: Name and path of the output file.

Tool 4 – Gained and lost patches
• Landscape Before: Polygonal FC of the landscape in the earliest moment of analysis.
• Landscape After: Polygonal FC of the landscape in the latest moment of analysis.
• Gained Area Output Feature Class: Name and path of the output file.
• Lost Area Output Feature Cass: Name and path of the output file.
• Gained Patches Output Feature Class: Name and path of the output file.
• Lost Patches Output Feature Cass: Name and path of the output file.


The outputs are:
Tool 1 - A feature class with the metrics calculated for the two or three dates and the districts or squares assigned to a Type of Dynamic.
Tool 2 - A new field added to the output of Tool 1.
Tool 3 - A feature class with the polygons representing Perforations.
Tool 4 - Four feature classes representing all gains, all losses, gained patches and lost patches.
___


References:
• Machado R, Godinho S, Pirnat J, Neves N, Santos P. 2018. Assessment of landscape composition and configuration via spatial metrics combination: conceptual framework proposal and method improvement. Landscape Research 43, 652–664. https://doi.org/10.1080/01426397.2017.1336757

• Machado R, Bayot R, Godinho S, Pirnat J, Santos P, Sousa-Neves N. 2020. LDTtool: a toolbox to assess landscape dynamics. Environmental Modelling and Software, 133. https://doi.org/10.1016/j.envsoft.2020.104847

• Related content regarding a similar tool for QGIS:
Paixão L, Machado R. 2023. LDT4QGIS: An open-source tool to enhance landscape analysis. Ecological Informatics. 75 (2023) 102073. https://doi.org/ 10.1016/j.ecoinf.2023.102073
