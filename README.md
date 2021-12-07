# WET 1.0 & WET 2.0
WET 1.0 Link: https://code.earthengine.google.com/c028d40c9d6d8de09af17fad5aa9bcc9 <br>
WET 2.0 Tool Link: https://code.earthengine.google.com/4a4ec0582be42be707c90977afee3710 <br>
WET 2.0 Training Link: https://code.earthengine.google.com/9820ef86ebc6cfaa30ae81d79b463353 <br>

## Wetland Extent Tool (WET 1.0)
2019 Spring JPL Great Lakes Water Resources

The Wetland Extent Tool (WET 1.0) was developed by the Great Lakes Water Resources Team to increase the
efficiency of wetland mapping in Minnesota. WET is an automated tool hosted on Google Earth Engine (GEE)
that maps wetland change and extent using Sentinel-1 C-SAR backscatter ratios, Landsat 8 (OLI) indices, and a
LiDAR derived Topographic Wetness Index (TWI).

### Getting Started
#### Prerequisites
WET was created for use within Google Earth Engine, an open source cloud computing platform, and was
scripted in JavaScript. The GEE API can be accesed on the [homepage](https://earthengine.google.com/), where users can sign up and request
approval. Resources for getting started and navigating the platform can be found in the [GEE user guide](https://developers.google.com/earth-engine/guides/getstarted).

#### Inputs
| Dataset | Source | Parameter | Resolution |
| ------- | ------ | --------- | ---------- |
| Landsat 8 (OLI) | GEE | TCWGD, MNDWI | 30m |
| Sentinel-1 C-SAR | GEE | VV, VH | 10m |
| DEM (LiDAR) | Steve Kloiber | TWI | 3m |
| Field Data | Steve Kloiber |

### Deployment
#### Classification Scheme
Classified maps can be inspected using GEE's inspector tool on the right panel. The Classified Clusters 
layer will return an indexed number indicating which landcover class the pixel belongs to.
| Level-1 Classification Code Key | Code Key | Description |
| ------------------------------- | -------- | ----------- |
| Upland | 1 | Dry land |
| Open Water | 2 | Includes rivers, lakes, ponds |
| Wetland | 3 | Inundated Area |

#### Outputs
By default, the variable Classfied Clusters will contain the classified map for the date range that is
specified, which by default is the growing season of 2017. Users can alter the date range in lines 11 and
12 of the code to create other classification outputs. We recommend only selecting dates within Northern
Minnesota's growing season of 05/21 to 09/26, to avoid using imagery with snow.

#### Computation
If the region of interest is too large, the computation may time out on Google Earth Engine. To avoid this
issue, users may instead export the output to their Google Drive. A function for doing this can be found 
in lines 981 to 988.

### Authors
- Erica O'Connor - *Team Lead*
- Melissa Ferriter
- Alice Lin
- Christopher Notto
### Contact
- Name: Alice Lin
- Email: alin14@g.ucla.edu
### Acknowledgements
- Erika Higa and Nega Kasraee
- Bruce Chapman and Benjamin Holt
- Our project partners at the US Fish and Wildlife Service, Minnesota Department of Natural Resources, 
  Environmental Protection Agency, Ducks Unlimited, National Oceanic and Atmospheric Administration Office for Coastal Management, and the University of Montana

## Wetland Extent Tool 2.0 (WET 2.0)
2020 Spring JPL Great Lakes Water Resources II

The Wetland Extent Tool 2.0 utilizes Landsat 8, Sentinel 2, Sentinel 1 C-SAR to automate wetland classification in the entire Great Lakes Basin at 10 m resolution. The tool allows users to select date ranges and areas for analysis, outputs map visualizations of the classification, generates time series graphs of optical indices, and exports images to the user's Google Drive. Users can change topographic information used in the classification, which is trained and validated against field data from the entire Great Lakes Basin. Options for topographic input include the Dynamic Surface Water Extent (calculated from Landsat 8 data), and SRTM elevation and slope information. A dark object subtraction atmospheric correction for Sentinel-2 Level 1C data is coded and can be utilized for date ranges that are before 2019, where backlogs of Google Earth Engine data  create large gaps in data coverage.
WET 2.0 can create classifications for the entire Great Lakes Basin without exceeding processing times because the image stack that the Random Forest classifier is applied on was created separately for each lake basin representing January - December 2019 and stored as an asset that is imported. 
If the user would like to create updated or customized training image stacks, they can use the Training script to generate and export these images as new assets to import into the WET 2.0 tool. 

The Wetland Extent Tool 1.0 utilizes Landsat 8 and Sentinel 1 C-SAR to classify wetlands in the state of Minnesota at 30 m resolution. The tool contains the same GUI as WET 2.0 and has the same instructions for use. 

The tool uses a graphical user interface (GUI) so that users can easily add, process, classify, and export data. The interface contains four main parts: 

	1. a panel to set analysis parameters (time range and area of analysis)
	2. a panel to select analysis types (classification, NDVI, etc) and add images to map
	3. a panel to export images to Google Drive
	4. a time series chart generator that creates line graphs based on the user-entered time range, area of analysis, and selected parameter

The three optical indices calculated are the Normalized Difference Vegetation Index (NDVI), Modified Normalized Water Index (MNDWI), and the Tasseled Cap Wetness Greenness Difference (TCWGD), derived from Sentinel-2 MSI 10 m data. The tool utilizes Sentinel-1 C-SAR VV, VH, VV/VH bands at 10 m. 

### Required Packages
WET's processing and classification uses Google Earth Engine's free and publicly accessible data catalog, in addition to several pre-loaded asset Google Earth Engine files. These are openly shared and already coded into the tool. 
Users do not need to download data, but do need to have a Google Earth Engine account. 

### Parameters
No additional steps need to be taken to modify the code to enable it to run. Users can run the code and interact with the GUI to customize and run analyses. Users may customize the code to change some inputs, however none need to be modified for it run. The user interface contains brief instructions to guide users through their use of the tool.


### Contact
Name(s): Vanessa Valenti | Erica Carcelen | Kathleen Lange | Nicholas Russo <br>
E-mail(s): vvalenti@g.ucla.edu | ericacarcelen@gmail.com | katielange19@gmail.com | nickrusso@g.ucla.edu

