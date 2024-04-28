# passive-radiometer-trace-data
Traces of satellite radiometer data collected during the month of September 2023 
----------------

This repository contains accompanying resources to our work on spectrum sharing between Earth Exploration Satellite radiometers and potential commerical users. The files in the repository represent Level 1 Brightness Temperature Data collected from Earh Exploration Satellite Service radiometers operating near 23.8 GHz, with footprints within 100 km of latitude 42.36 deg, longitude -70.06 deg (i.e. Boston), during the month of September 2023. 

The radiometers represented in these traces are sourced from the below publicly available repositories. The data represented in these traces represents a subset of the available data from the radiometers, and a subset of the radiometers operating on the selected frequency range. These are intended to represent a sample of usage behavior near 23.8 GHz within a selected footprint range. Additional trace data will be added as the team gains access, however we do not claim that the traces represent a definitive record of usage near 23.8 GHz by radiometers within a 100km footprint distance of Boston.

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

---------------------
# Data Format

The matricies consist of the following

* bstoretb - the brightness data, confirming that the statellite radiometer is active in that point in time; the units vary depending on the sensor in question  
* bstorelat - the radiometer footprint latitudinal position  
* bstorelon - the radiometer footprint longitudinal position  
* bstoredist - the radiometer footprint distance from (-70.06,42.36)  
* bstoretime - the time of the measurement, in datenum format (i.e. Number of days since 0000-01-00 in the proploetic ISO 8601 calendar; time of day converted into decimals)  
* bstoresat - the identifier of the radiometer in satname  
* satname - a 1x14 cell translating the numerical identifier in bstoresat to the radiometer or sensor name from the above table:

  satname Index | satname Entry | Satellite
  --- | --- | ---
  1 | 'AMSR2_traces.mat' | GCOM-W
  2 | 'AQUA_traces.mat' | Aqua
  3 | 'ATMS_JPSS1_traces.mat' | JPSS-1 (NOAA 20)
  4 | 'ATMS_SNPP_traces.mat' | SNPP
  5 | 'GMI_traces.mat' | GPM Core Observatory
  6 | 'JPSS2_traces.mat' | JPSS-2 (NOAA 21)
  7 | 'METOP_B_traces.mat' | Metop-B
  8 | 'METOP_C_traces.mat' | Metop-C
  9 | 'N15_traces.mat' | NOAA-15
  10 | 'NOAA18_traces.mat' | NOAA-18
  11 | 'NOAA19_traces.mat' | NOAA-19
  12 | 'S3A_traces.mat' | Sentinel-3A
  13 | 'S3B_traces.mat' | Sentinel-3B
  14 | 'S6_traces.mat' | Sentinel-6A

These matrix files are combined to analyze the trace data. For instance, at 13\:13\:55 on 2023-09-10, the GPM Core Observastory GMI radiometer was observed with a footprint location at (-70.4478, 43.036), a distance of 90.2448 km from (-70.06,42.36), and Level 1 Brightness data of 238.2118. This is the 28710th individual data point in the trace data set. Thus, this is reflected in the matricies as follows (assuming long format display for bstoretime)

* bstoretb(28710) = 238.2118  
* bstorelat(28710) = 43.0360  
* bstorelon(28710) = -70.4478  
* bstoredist(28710) = 90.2448  
* bstoretime(28710) = 7.391395513379229e+05  
* bstoresat(28710) = 5  
* satname(5) = 'GMI_traces.mat'

-----------------
# License


These materials may be freely used and distributed, provided that attribution to this original source is acknowledged. If you use the data in this repository, we kindly ask that you refer to the following work (cf. the included citation.bib file in this repository):

Jonathan Chamberlain, Joel T Johnson, David Starobinski. "Spectrum Sharing between Earth Exploration Satellite and Commercial Services: An Economic Feasibility Analysis". *IEEE International Symposium on Dynamic Spectrum Access Networks (DySPAN) 2024*. Washington, DC, USA. May 2024.  

-----------------
# References

If you are using these traces in your work and would like to be featured in this list, kindly create an issue in this repository and provide us with the reference if you would like it to be featured here.

-----------------
# Acknowledgment

Support by the US National Science Foundation is gratefully acknoweldged (project ids: AST-2229103 and AST-2229104)
