# passive-radiometer-trace-data
Trace data of satellite radiometer data colleted during the month of September 2023 
----------------

The files in this repository are MATLAB matrix files corresponding to Level 1 Brightness Temperature Data collected from 
Earh Exploration Satellite Service radiometers operating near 23.8 GHz within 100 km of latitude 42.36 deg, longitude -70.06 deg (i.e. Boston)

The radiometers represented in these traces are the following, sourced from publicly available repositories

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


The matricies consist of the following

bstoreb - the brightness data, confirming that the statellite radiometer is active in that point in time
bstorelat - the radiometer's latitudinal position
bstorelon - the radiometer's longitudinal position
bstoredist - the radiometer's distance from (-70.06,42.36)
bstoretime - the time of the measurement
bstoresat - the identifier of the radiometer
satname - a 1x14 cell translating the numerical identifier in bstoresat to the radiometer name from the above table.

Within each .mat file, a single line consists of a single satillite's data points in a given point in time; e.g. the position for the satellite entry noted in line 100 of bstoretime is given by line 100 of bstorelat and bstorelon. As each data point consists of a single teperature measurement, a sweep of the area will consist of multiple line entries.
