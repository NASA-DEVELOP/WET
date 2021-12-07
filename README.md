# Wetland Extent Tool (WET)
**NASA DEVELOP Spring 2019** <br>
WET Link: https://code.earthengine.google.com/c028d40c9d6d8de09af17fad5aa9bcc9 <br>

The Wetland Extent Tool (WET) was developed by the Great Lakes Water Resources Team to increase the
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


