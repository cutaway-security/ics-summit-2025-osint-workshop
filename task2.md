---
layout: default
---

# OSINT Workshop
[Agenda](./index.md)

## Task 2: ICS / OT Passive Geolocation Reconnaissance By Sector

Industrial control environments have large footprints. These facilities can be large. Google Maps provides [satellite views](https://www.google.com/maps/@27.8950877,-97.2678658,3746m/data=!3m1!1e3?entry=ttu&g_ep=EgoyMDI1MDQzMC4xIKXMDSoASAFQAw%3D%3D){:target="_blank"} of public areas. These views provide information about ingress and egress from industrial sites. Understanding the address of a site allows the area to be searched using a top-down view. It also may provide a street view of the location which can show parking areas, guard shacks, cameras, and other details about the site. While this information can be dated it is often current enough make basic assumptions about physical security.

The complexity of critical infrastructure and the societies dependency on the delivery of many services means that information needs to be shared across organizations. There are public and private services that can provide details about different types of infrastructures. Information about private industries is often publicized through media, business research, and governmental oversight. If it is on the internet, it is available to everyone. Some of these sites require accounts and may require approval to access the information. Other sites are maintained as open project that may not require accounts. These services vary but the can provide interesting details about the size, scope, and deployment of technologies in different sectors. While this information may be dated, it is a starting point. 

### Self-paced Questions 

Review the following resources in the [maps and data section](#industrial-resource-maps-and-data-sites) to understand some of the internet accessible geolocation resources for each sector. Consider for some of these questions during your analysis. If these are too basic, come up with your own questions.

* Hunt for resources in your state or country?
    * What is the closest substation to your home?
    * What is the closest refinery to your home?
    * Where is the closest farm to your home? - besides your home :wink:
* Are we missing sectors?
* Can you find other mapping resources for these and other sectors?

### AI Analysis Query 

Using an AI tool, run the following query to help identify areas of focus. These results should be used to help organize your thoughts and also remind you of some of the online resources you may have forgotten or did not know about. Modify this statement by changing `chicken ranches` to a different area of focus and `Texas` to the geolocation of your choice.

> Provide me recommendations for online mapping resources to understand the distribution of large chicken ranches in Texas.

## Google Maps

[Google Maps](https://www.google.com/maps){:target="_blank"} offers three different layer views: map view, satellite view, and street view. The satellite view may show features in and around a specific site in an overhead view. Check the site for dumpsters, guard shacks, fence lines, trees, creeks, and other areas that are good for access or monitoring. When in street view, the tool may provide additional (older) versions of the site. Reviewing the street view on different dates may illustrate what has changed with the building over time. It could help you understand when equipment, such as cameras and badge readers, were added or removed.

**HINT:** Do not forget to angle the street view up to see cameras on fence and pole tops.

## Industrial Resource Maps and Data Sites

### Electrical

* [ARCGIS.com](https://www.arcgis.com/index.html){:target="_blank"} - interactive maps
    * [U.S. Electric Power Transmission Lines](https://www.arcgis.com/apps/mapviewer/index.html?layers=d4090758322c4d32a4cd002ffaa0aa12){:target="_blank"}
* State Public Utility Resources
    * [Texas Electricity Supply Chain Map](https://www.puc.texas.gov/industry/maps/supplychain/){:target="_blank"}
* [Open Infrastructure Map](https://openinframap.org){:target="_blank"} - a view of the world's infrastructure mapped in the [OpenStreet Database](https://www.openstreetmap.org/){:target="_blank"}
    * [Infrastructure in Corpus Christi, Texas](https://openinframap.org/#9.86/27.706/-97.3027){:target="_blank"}
* [U.S. Energy Atlas](https://atlas.eia.gov/pages/energy-maps) - "a comprehensive reference for data and interactive maps of energy infrastructure and resources in the United States."
    * [Electricity](https://atlas.eia.gov/apps/895faaf79d744f2ab3b72f8bd5778e68/explore){:target="_blank"}
    * [Renewable Electricity Infrastructure and Resources Dashboard](https://eia.maps.arcgis.com/apps/dashboards/77cde239acfb494b81a00e927574e430){:target="_blank"}

### Pipelines

* [Pipeline101.org](https://pipeline101.org/location/){:target="_blank"} - "Nearly the entire mainline pipe is buried. Other pipeline components such as pump stations are above ground. Some lines are as short as a mile, while others may extend 1,000 miles or more."
* [ARCGIS.com](https://www.arcgis.com/index.html){:target="_blank"} - interactive maps
    * [Texas Natural Gas Pipelines](https://www.arcgis.com/apps/mapviewer/index.html?webmap=f7a56b06db5a44a598b99abc5fe0a132){:target="_blank"}
* [National Pipeline Mapping System](https://www.npms.phmsa.dot.gov/){:target="_blank"} - " a dataset containing locations of and information about gas transmission and hazardous liquid pipelines, Liquefied Natural Gas (LNG) plants, and breakout tanks which are under the jurisdiction of the Pipeline and Hazardous Materials Safety Administration (PHMSA)"
    * [National Pipeline Mapping System (NPMS) Public Viewer](https://pvnpms.phmsa.dot.gov/PublicViewer/){:target="_blank"} - select state then county
* [U.S. Energy Atlas](https://atlas.eia.gov/pages/energy-maps) - "a comprehensive reference for data and interactive maps of energy infrastructure and resources in the United States."
    * [Crude Oil Pipelines](https://atlas.eia.gov/datasets/eia::crude-oil-pipelines/explore){:target="_blank"}
    * [Natural Gas](https://atlas.eia.gov/apps/3652f0f1860d45beb0fed27dc8a6fc8d/explore){:target="_blank"}

### Roadways

* Bureau of Transportation Statistics: 
    * [Transportation Geography of the United States](https://www.bts.gov/geography/geospatial-2/transportation-geography-united-states-2025){:target="_blank"}
    * [Major roadways and border crossings PDF](https://www.bts.gov/sites/bts.dot.gov/files/docs/Transportation_Geography_of_the_United_States_2025.pdf){:target="_blank"}
            
### Airport Maps
* Wikipedia [List of airports in the United States](https://en.wikipedia.org/wiki/List_of_airports_in_the_United_States){:target="_blank"}
* [ARCGIS.com](https://www.arcgis.com/index.html){:target="_blank"} - interactive maps
    * [Airports Map View](https://www.arcgis.com/apps/View/index.html?appid=cba647d88bcb4c819b01dcfba019c456){:target="_blank"}
* [Leonard's Guide to Airport Codes](https://www.leonardsguide.com/us-airport-codes.shtml){:target="_blank"} - List of three-letter airport codes covering the United States

### Chemical Manufacturing
* [Dun&Dradstreet U.S. Chemical Manufacturing Companies List](https://www.dnb.com/business-directory/company-information.chemical_manufacturing.us.html){:target="_blank"}
* [IndustrySelect Top 10 Chemical Manufacturing Plants in US](https://www.industryselect.com/blog/top-10-chemical-manufacturers-in-the-us){:target="_blank"}
* [EPA](https://www.epa.gov/){:target="_blank"}
    * [Chemicals, Pesticides and Toxic Topics](https://www.epa.gov/environmental-topics/chemicals-pesticides-and-toxics-topics){:target="_blank"}
    * [EPA TRI Explorer Release Reports](https://enviro.epa.gov/triexplorer/tri_release.chemical){:target="_blank"}
    * [Nueces County, Texas](https://enviro.epa.gov/triexplorer/release_chem?p_view=COCH&trilib=TRIQ1&sort=_VIEW_&sort_fmt=1&state=48&county=48355&chemical=All+chemicals&industry=ALL&year=2023&tab_rpt=1&fld=RELLBY&fld=TSFDSP){:target="_blank"}

### Food Supply
* Cold Storage
    * [Top 10 Cold Change Logistics Companies in USA](https://www.hopstack.io/blog/top-cold-chain-companies-us){:target="_blank"}
    * [Global Cold Chain Alliance](https://www.gcca.org/resource/2023-gcca-north-american-top-25-list-of-refrigerated-warehousing-and-logistics-providers-2/){:target="_blank"}
* [Texas Farm Finder](https://www.txfarmfinder.com/product-maps){:target="_blank"}
* [Texas Department of Agriculture: Farm Fresh Network](https://www.squaremeals.org/FandN-Resources/Texas-Farm-Fresh/Texas-Farm-Fresh-Network/Map-of-Texas-Farm-Fresh-Network-Members){:target="_blank"}
* [Factory Farm Nation: 2024 Edition](https://storymaps.arcgis.com/stories/cc02f97b1129447db2420eb8b6b258e1){:target="_blank"}


### Oil and Gas
* [National Energy and Petrochemical Map](https://www.arcgis.com/apps/webappviewer/index.html?appid=0cdff7e116c0425fa55d1226e9204477){:target="_blank"}
* [Wells in Texas](https://ft.maps.arcgis.com/apps/instant/sidebar/index.html?appid=d40eb3dcd8084c2fbd952c56f65bbb89){:target="_blank"}
* Comprehensive List of Refineries in Texas
    * [Arnold and Itkin LLP](https://www.arnolditkin.com/blog/plant-accidents/comprehensive-list-of-refineries-in-texas/){:target="_blank"}
    * [The White Law Firm](https://www.wilhitelawfirm.com/blog/list-of-texas-refineries/){:target="_blank"}
* [Texas Railroad Commission of Texas Maps Data](https://www.rrc.texas.gov/oil-and-gas/publications-and-notices/maps/){:target="_blank"}

### Water
* [Water / Waste Water Maps](https://www.waterandwastewater.com/us-wastewater-treatment-plants-map/){:target="_blank"}
* [EPA](https://www.epa.gov/){:target="_blank"}
    * [Water Topics](https://www.epa.gov/environmental-topics/water-topics){:target="_blank"}
    * [My Waterway](https://mywaterway.epa.gov/){:target="_blank"}
        * [Nueces County, Texas Drinking Water](https://mywaterway.epa.gov/community/Corpus%20Christi,%20TX,%20USA%20(Nueces%20County)/drinking-water){:target="_blank"}
* [Facility Reports](https://ordspub.epa.gov/ords/sfdw_rest/r/sfdw/sdwis_fed_reports_public/6?p6_report=FAC){:target="_blank"}
    * [Corpus Christi Facility Reports](https://ordspub.epa.gov/ords/sfdw_rest/r/sfdw/sdwis_fed_reports_public/fd?ireq_pwsid=TX1780003&clear=12,RIR){:target="_blank"}
* [AWWA Water Map](https://experience.arcgis.com/experience/a54e850eed3f493db0835e8c6b08c2ba){:target="_blank"}
* [Texas Public Utility Commission - Water and Sewer CNN Viewer](https://www.puc.texas.gov/industry/water/utilities/map.aspx){:target="_blank"}
* [Texas Wastewater Outfalls](https://experience.arcgis.com/experience/262c0c7bfddf4d6da7f59552f652f197/){:target="_blank"}

## Next Step

When you are done, move onto [Task 3](task3.md): Student Target Identification.