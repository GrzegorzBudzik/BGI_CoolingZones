BGI_CoolingZones

This ArcGIS Python script automates the process of analyzing Land Surface Temperature (LST) data to identify cooling zones and calculate the cooling potential of parks within a given region. It processes multiple LST raster datasets and corresponding park boundary layers to generate meaningful insights into the cooling effects of blue-green infrastructure.

Requirements
ArcGIS Pro (with Spatial Analyst extension)
Python 3.x (comes with ArcGIS Pro)
Input Data:
A geodatabase containing the LST rasters and park boundary layers.
LST raster files named in the format LST_YYYMMDD, where YYYMMDD represents the acquisition date.

Installation
Clone this repository or download the script file.

Prepare Your Data:
Ensure that all your LST raster files and the park boundary layer are in the same geodatabase.
The LST raster files should be named following the pattern: LST_YYYMMDD.

Usage
1. Script Inputs
The script requires the following inputs, which can be provided through the ArcGIS Pro interface:
Geodatabase Path (gdb_path): Path to the geodatabase containing your LST rasters and park layers.
Park Layer Input (park_layer_in_path): The input park boundary layer.
Park Layer Output (park_layer): The output park boundary layer after processing.
Cooling Zones Prefix (cooling_zones_prefix): A prefix for naming the output cooling zones layers.

2. Running the Script
Open ArcGIS Pro and set the appropriate geodatabase as your workspace.
Load the script into the Python window or run it as a script tool if set up that way.
Provide the required inputs:
Geodatabase Path
Park Layer Input
BGI Layer Output
Cooling Zones Prefix
Execute the script. It will process each LST raster, generating cooling zones and calculating cooling potential for each BGI in the dataset.

3. Output
Cooling Zones: Feature layers representing cooling zones for each LST raster, named using the provided prefix and acquisition date.
BGI Layer with Cooling Potential: The BGI boundary layer with additional fields representing the cooling potential metrics:
HCDMAX_YYYMMDD: Maximum cooling distance.
HCI_YYYMMDD: Cooling index.
CA_YYYMMDD: Cooling area.
CA_AR_YYYMMDD: Cooling area ratio.
Example
If your geodatabase is located at C:\GISData\UrbanCooling.gdb, and your input BGI layer is BGIs, your script input values might look like this:

Geodatabase Path: C:\GISData\UrbanCooling.gdb
BGI Layer Input: BGIs
BGI Layer Output: BGIs_Processed
Cooling Zones Prefix: CoolingZones_
The output layers will be stored in the same geodatabase, with names like CoolingZones_20230904 (for a raster from September 4, 2023).

Notes
Parallel Processing: The script is optimized to use 100% of available processing power for faster execution.
Error Handling: If an error occurs during the Zonal Statistics step, the script will skip that particular BGI and continue processing the rest.
License
This script is provided as-is under the MIT License. Feel free to use and modify it as needed for your own projects.

Support
For any issues or questions, please contact Grzegorz Budzik at grzegorz.budzik@upwr.edu.pl.
