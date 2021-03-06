## Background
The data analysis performed by the scripts below replicates a study by Nate Silver of [FiveThirtyEight.com](http://fivethirtyeight.com) on the subject of urban diversity and segregation. The original study explored ethnic diversity at citywide vs. neighborhood levels in the 100 most populous American cities. Building on this work, the current analysis explores diversity for the largest Canadian and UK cities. 

Given the smaller sizes of Canada and the UK relative to the USA, the 10 most populous cities were chosen in each smaller country for analysis. This threshold resulted in the smallest cities analyzed having approximately the same population as the smallest cities analyzed in the American study, on the order of 500,000 people. Also, it's worth noting that comprehensive statistics on ethnicity in the UK are available only for the nations of England and Wales, so these nations were the focus of the present study. All cities were treated as metropolitan areas.

For more information about the original analysis by [FiveThirtyEight.com](http://fivethirtyeight.com), please see this article:
* http://fivethirtyeight.com/features/the-most-diverse-cities-are-often-the-most-segregated/

For a writeup of the new analysis, please see this blog post:
* http://modjeska.typepad.com/icosahedron/2015/10/city-diversity-vs-segregation-in-the-usa-canada-and-the-uk.html

## Raw Data

The Canadian data used in this analysis were obtained from government census and geographic repositories:

* http://www12.statcan.gc.ca/nhs-enm/2011/dp-pd/prof/details/download-telecharger/comprehensive/comp-csv-tab-nhs-enm.cfm?Lang=E
  * 99-004-XWE2011001-401_CSV.ZIP (interactive download only)
* http://www12.statcan.gc.ca/census-recensement/2011/geo/bound-limit/files-fichiers/gct_000b11a_e.zip
* http://www12.statcan.gc.ca/census-recensement/2011/geo/bound-limit/files-fichiers/gcsd000b11a_e.zip

The UK data used in this analysis were obtained from government census and geographic repositories:

* http://www.ons.gov.uk/ons/rel/census/2011-census/key-statistics-and-quick-statistics-for-wards-and-output-areas-in-england-and-wales/rft-ct0010-wards.zip
* www.ons.gov.uk/ons/external-links/social-media/g-m/2011-built-up-areas-to-2011-lads.html
  * OA11_WD11_LAD11_EW_LU.csv (interactive download only)
* http://www.ons.gov.uk/ons/external-links/social-media/g-m/2011-oas-to-2011-wards--with-best-fit-percentage-indicator-.html
  * OA11_BUASD11_BUA11_LAD11_RGN11_EW_LU.csv (interactive download only)
* http://www.ons.gov.uk/ons/external-links/social-media/g-m/2011-census-merged-ward-boundaries---generalised--20-metres---clipped-to-the-coastline.html (interactive download only via http://www.ons.gov.uk/ons/guide-method/geography/products/census/spatial/2011/index.html)

The American data used in this analysis were obtained from Brown University's research on the government's census data (i.e., American Community Survey):

* www.s4.brown.edu/us2010/Data/WPdownload/msa10p.xls

UK and Canadian data were downloaded in May 2015, and American data were downloaded in February 2016.

## R Scripts

The following R scripts are used in this data analysis. They're located in the [**scripts**](scripts) folder

* [**canada_processing.R**](scripts/canada_processing.R):  get and process Canada census data
* [**canada_analysis.R**](scripts/canada_analysis.R):  analyze Canada processing data, and output graphics and tables
* [**england_processing.R**](scripts/england_processing.R):  get and process UK census data
* [**england_analysis.R**](scripts/england_analysis.R):  analyze UK processing data, and output graphics and tables
* [**usa.R**](scripts/usa.R):  get, process, and analyze USA census data
* [**summary_presentation.R**](scripts/summary_presentation.R):  output summary graphics for USA, Canada, and UK (and create a linear regression model)

These scripts assume that the interactive-download data mentioned above is present in the "Canada Data", "England Data", and "USA Data" folders under the working directory. 

These scripts also assume that the following file is present in the working directory, in order to map from approximately 100 UK ethnicities into 5 Canadian visible minorities:

* [**england_ethnicity_mappings.csv**](scripts/england_ethnicity_mappings.csv)

The scripts can be run in the order indicated below, for example. The England scripts can also be run before the Canadian ones successfully, or the USA script before any non-summary script.

1. canada_processing.R
2. canada_analysis.R
3. england_processing.R
4. england_processing.R
5. usa.R
5. summary_presentation.R

To run canada_processing.R in an R environment, for example, use the following command:

```
source("canada_processing.R")
```

## Presentation Files
Graphical and textual output from this data analysis can be found in the following folders:

* [**presentation**](presentation): summary charts and tables for USA, Canada, and UK
* [**canada_city_maps**](canada_city_maps): maps for Canadian cities
* [**canada_exploratory_plots**](canada_exploratory_plots): exploratory plots for Canadian cities
* [**england_city_maps**](england_city_maps): maps or UK cities
* [**england_exploratory_plots**](england_exploratory_plots): exploratory plots for UK cities


