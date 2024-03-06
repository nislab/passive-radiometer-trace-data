# passive-radiometer-trace-data
Trace data of satellite radiometer data colleted during the month of September 2023 
----------------

This repository contains accompanying resources to our work on spectrum sharing between Earth Exploration Satellite radiometers and potential commerical users. The files in the repository represent Level 1 Brightness Temperature Data collected from 
Earh Exploration Satellite Service radiometers operating near 23.8 GHz, with footprints within 100 km of latitude 42.36 deg, longitude -70.06 deg (i.e. Boston), during the month of September 2023. 

The radiometers represented in these traces are sourced from the below publicly available repositories. The data represented in these traces represents a subset of the available data from the radiometers, and a subset of the radiometers operating on the selected frequency range. 
These are intended to represent a sample of usage behavior near 23.8 GHz within a selected footprint range. Additional trace data will be added as the team gains access, however we do not claim that the traces represent a definitive record of usage near 23.8 GHz by radiometers 
within a 100km footprint distance of Boston.

Satellite | Space Agency | Sensor 
--- | --- | --- 
[Aqua](https://disc.gsfc.nasa.gov/datasets/AIRABRAD005/summary)| NASA | AMSU-A
[GCOM-W](https://gportal.jaxa.jp/gpr/search?tab=1) | JAXA | AMSR2 
[GPM Core Observatory](https://disc.gsfc.nasa.gov/datasets/GPM1BGMI07/summary) | NASA | GMI 
[Metop-B](https://data.eumetsat.int/product/EO:EUM:DAT:METOP:AMSUL1) |EUMETSAT | AMSU-A 
[Metop-C](https://data.eumetsat.int/product/EO:EUM:DAT:METOP:AMSUL1) | EUMETSAT | AMSU-A 
[NOAA-15](https://www.ncei.noaa.gov/has/HAS.FileAppRouter?datasetname=NSTARFCDR&subqueryby=STATION&applname=&outdest=FILE) | NOAA | AMSU-A 
[NOAA-18](https://www.ncei.noaa.gov/data/amsu-a-brightness-temperature/access) | NOAA | AMSU-A  
[NOAA-19](https://www.ncei.noaa.gov/data/amsu-a-brightness-temperature/access) | NOAA | AMSU-A 
[JPSS-1 (NOAA 20)](https://www.ncei.noaa.gov/access/metadata/landing-page/bin/iso?id=gov.noaa.ncdc:C0142) | NOAA | ATMS 
[JPSS-2 (NOAA 21)](https://www.ncei.noaa.gov/access/metadata/landing-page/bin/iso?id=gov.noaa.ncdc:C0142) | NOAA | ATMS 
[Sentinel-3A](https://documentation.dataspace.copernicus.eu/Data/Sentinel3.html#sentinel-3-sral-level-2) | ESA | MWR 
[Sentinel-3B](https://documentation.dataspace.copernicus.eu/Data/Sentinel3.html#sentinel-3-sral-level-2) | ESA | MWR 
[Sentinel-6A](https://navigator.eumetsat.int/product/EO:EUM:DAT:0146) | EUMETSTAT | AMR-C 
[SNPP](https://www.ncei.noaa.gov/data/amsu-a-brightness-temperature/access) | NOAA | ATMS 


# Data Format
---------------------
The matricies consist of the following

* bstoreb - the brightness data, confirming that the statellite radiometer is active in that point in time  
* bstorelat - the radiometer footprint latitudinal position  
* bstorelon - the radiometer footprint longitudinal position  
* bstoredist - the radiometer footprint distance from (-70.06,42.36)  
* bstoretime - the time of the measurement, in datenum format (i.e. Number of days since 0000-01-00 in the proploetic ISO 8601 calendar; time of day converted into decimals)  
* bstoresat - the identifier of the radiometer in satname  
* satname - a 1x14 cell translating the numerical identifier in bstoresat to the radiometer name from the above table.  

These matrix files are used together to analyze 

# Liscene
-----------------

These materials may be freely used and distributed, provided that attribution to this original source is acknowledged. If you use the data in this repository, we kindly ask that you refer to the following work:

Jonathan Chamberlain, Joel T Johnson, David Starobinski. "Spectrum Sharing between Earth Exploration Satellite and Commercial Services: An Economic Feasibility Analysis". *IEEE International Symposium on Dynamic Spectrum Access Networks (DySPAN) 2024*. Washington, DC, USA. May 2024.  

# References
-----------------

If you are using these traces in your work and would like to be featured in this list, kindly create an issue in this repository and provide us with the reference if you would like it to be featured here.
