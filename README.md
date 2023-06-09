# LCannabis

Environmental Burden of Indoor Cannabis Production - Original work from Summers et al 2021 found here https://github.com/haisummers

This repository contains code to replicate the analysis from: VDB et al 2023 manuscript

Requirements
This code was first developed in Matlab R2017a by Summers et al.(2021),"The greenhouse gas emissions of indoor cannabis production in the United States". 
It was adapted by VDB et al. (2023) in MatlabR2022b to be used with Canadian weather information. 
Outputs are written in an .xlsx format and will need Microsoft Excel to open.

• Basic Replication

File Extraction and Set Up: These instructions will generate results for the 99 locations analyzed in the analysis. Download the "LCannabis_VDB.zip" and "TMY3_VDB.zip" and extract all files to one folder. "TMY3." is a folder containing 99 weather data files from Canada, the 1011 weather data file from the US can be found in "TMY3" from Hailey Summers github (see top of page) but need to be run with the original code. After unziping, you should have a root folder with the files from "Indoor Cannabis Analysis - VDB.zip" (the files listed below in the supporting files section) and a folder among this files titled "TMY3." Inside the "TMY3" folder should be 99 .csv files. This structure is mandatory for the Matlab files and functions to read data from.

Open the “indoor_cannabis_all_locations_VDB.m” file through Matlab and run. As is, this file will run all 99 canadian locations and print results to an Excel File titled "Outputs.xlsx." The "Outputs.xlsx" file will be generated in the root folder where the "indoor_cannabis_all_location_VDBs.m" is located. Printed in the file are TMY3 file name, city name, state, greenhouse gas emissions (kg CO2-eq/kg- dried flower), electricity (kWh/kg-dried flower), natural gas required (MJ/kg-dried flower) and CO2 fottprint of 37 additional parameters from the "Indoor_Model_Facility_LCAv5_VDB" for all locations. "Outputs from VDB manuscript.xlsx" is provided as a guide for validation and data extraction from the code output found in "Output.xlsx" after the code ran completely. These are the results generated from the original analysis for all 99 canadian locations. Data from natural gas (NG) and electricity (kWh) consumption were used as inputs in a OpenLCA model.

• Supporting Files

Indoor_Model_Facility_LCAv5_VDB - Matlab function that is the indoor cannabis growth model, performs all material and energy inventory calculations, runs for each location, more info in the commented header of this file
Indoor Cannabis Model.xlsx - primary data file that Matlab reads from for input variables
Psychrometricsnew.m - Matlab function that returns any property from a psychrometric chart, required two variables to fix state and a pressure
vdb_Zipcodes.xlsx - Zipcode, latitude and longitude matched locations that is a database of electricty grid emissions GHGs/kWh
electricityLCIegrid26regionstotal.m - electricity grid emissions matched based on Zipcodes.xlsx and latitude and longitude of TMY3 - not this file has the same name as in the original code but was modified, check comments 
