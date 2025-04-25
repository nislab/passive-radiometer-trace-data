# passive-radiometer-trace-data
Traces of satellite radiometer data collected during the months of September and October 2023 
----------------

This repository contains accompanying resources to our joint work with the Ohio State [ElectroScience Laboratory](https://electroscience.osu.edu/) on spectrum sharing between Earth Exploration Satellite radiometers and potential commercial users. The files in the repository represent Level 1 Brightness Temperature Data collected from Earh Exploration Satellite Service radiometers operating near 23.8 GHz, with footprints within 100 km of selected locations. 

The repository consists of two collections of data. 

The first, the single-month-traces, consist solely of traces data corresponding to footrprint data collected near latitude 42.36 deg, longitude -70.06 deg. (i.e., Boston MA, United States) during the month of September 2023, and was used as the basis for the analysis of the radiometer characterization in the 2024 DySpan work noted below.

The second, the two-month-traces represents our first major update to the collection for analysis and data processing, consisting of footprint data collected near the following locations during the months of September-October 2023:

Location | Identifier | Latitude | Longitude
--- | --- | --- 
Barcelona, Spain | BAR | 41.38 | 2.17
Boston MA, United States | BOS | 42.36 | -71.06
Cheyenne WY, United States | WYO | 41.14  | -104.82
Chicago IL, United States | CHI | 41.87  | -87.64
Columbus OH, United States | CLB | 40.00 | -83.02
Dallas TX, United States | DAL | 32.78  | -96.80
Edmonton AB, Canada | EDM | 53.53  | -113.50
Fairbanks AK, United States | FAK | 64.83  | -147.70
Mexico City, Mexico | CDM | 19.42 | -99.14
Omaha NE, United States | NEB |  41.26  | -95.95
Pituffik, Greenland | PIT | 76.53  | -68.82
Quito, Ecuador | SFQ | -0.25  | -78.47
Rome, Italy | RME |  41.92  | 12.48
Salt Lake City UT, United States | SLC | 40.76  | -111.89
Sofia, Bulgaria | SOF | 42.71 | 23.32

The radiometers represented in these traces are sourced from the below publicly available repositories. The data represented in these traces represents a subset of the available data from the radiometers, and a subset of the radiometers operating on the selected frequency range. These are intended to represent a sample of usage behavior near 23.8 GHz within a selected footprint range. Additional trace data will be added as the team gains access; however we do not claim that the traces represent the definitive record of usage near 23.8 GHz by radiometers within a 100km footprint distance of the sampled locations.

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
[SWOT](https://podaac.jpl.nasa.gov/dataset/SWOT_L2_RAD_GDR_2)^1 | NASA | AMR

1: Only included in the two-month trace set

---------------------
# Data Format

The matrices consist of the following (where XXX is the Identifier for two-month-traces data; the single-month-traces data file names omits this tag)

* XXXbstoretb - the brightness data, confirming that the statellite radiometer is active in that point in time; the units vary depending on the sensor in question  
* XXXbstorelat - the radiometer footprint latitudinal position  
* XXXbstorelon - the radiometer footprint longitudinal position  
* XXXbstoredist - the radiometer footprint distance from (-70.06,42.36)  
* XXXbstoretime - the time of the measurement, in datenum format (i.e. Number of days since 0000-01-00 in the proploetic ISO 8601 calendar; time of day converted into decimals)  
* XXXbstoresat - the identifier of the radiometer in satname  
* XXXsatname - a 1xN cell translating the numerical identifier in bstoresat to the radiometer or sensor name from the above table:

satname Entry | Satellite
--- | ---
'AMSR2_traces.mat' | GCOM-W
'AQUA_traces.mat' | Aqua
'ATMS_JPSS1_traces.mat' | JPSS-1 (NOAA 20)
'ATMS_SNPP_traces.mat' | SNPP
'GMI_traces.mat' | GPM Core Observatory
'JPSS2_traces.mat' | JPSS-2 (NOAA 21)
'METOP_B_traces.mat' | Metop-B
'METOP_C_traces.mat' | Metop-C
'N15_traces.mat' | NOAA-15
'NOAA18_traces.mat' | NOAA-18
'NOAA19_traces.mat' | NOAA-19
'S3A_traces.mat' | Sentinel-3A
'S3B_traces.mat' | Sentinel-3B
'S6_traces.mat' | Sentinel-6A
'SNPP_traces.mat' | SNPP
'SWOT_traces.mat' | SWOT

The index corresponding to the identifier in satname is unique per location due to ordering issues/certain missions not recording data for selected locations in the sample period. As such, it is necessary to ensure that all data is being correlated to the same location. 

These matrix files are combined for trace data processing and analysis. 

For instance, at 13\:13\:55 on 2023-09-10, the GPM Core Observastory GMI radiometer was observed with a footprint location at (-70.4478, 43.036), a distance of 90.2448 km from (-70.06,42.36), and Level 1 Brightness data of 238.2118. This is the 28710th individual data point in the trace data set within the single-month-traces. This is reflected in the corresponding matricies as follows (assuming long format display for bstoretime)

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

If specifically using the two-month-traces data, the following alternative citation is appropriate:

Nicholas Brendle, Jonathan Chamberlain, Joel T Johnson, David Starobinski. "Advancing Spectrum Sharing through Statistical Analysis of EESS-Passive Satellite Overpasses." *IEEE International Symposium on Dynamic Spectrum Access Networks (DySPAN) 2025* London, United Kingdom. May 2025.

-----------------
# References

If you are using these traces in your work and would like to be featured in this list, kindly create an issue in this repository and provide us with the reference.

-----------------
# Acknowledgment

Support by the US National Science Foundation is gratefully acknoweldged (project ids: AST-2229103 and AST-2229104)
