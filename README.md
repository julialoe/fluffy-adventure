# fluffy-adventure

Automated version of MTXQCvX2 - fluffy adventure

## Version and updates

### 2018-10-22 - major update

Version: 1.0.2

I have included first files of documentation in the folder man/vignettes. You need to knit each `.Rmd`. file in order read
these files in a comfortable format. You might to need to run `install.packages("tufte")` prior rendering a file.

Furthermore I have implemented smaller bug fixes, typos and such kind of things.


### 2018-10-16 - major update

*Important fix in case you have issues with MTXQCvX2_part3 - ManualValidation of PeakAreas*

Integration of warning messages if you have the following issue:
  * multiple values for a single metabolite and file in ManVal_PeakAreas.csv
  * resulting in a warning: aggregation function missing
  * cause a malfunction of the integration of peakareas into original file
  
The fix shows now detailed warning messages and where to check to fix the issue.

If warning occurs:
  * check Aggregationfailure.csv file created in project-folder/output
  * mean_val reflects average value for metabolite across the project
  * mean_val shows values in single, double digits: these are duplicated values
  * fix these duplicates values per metaboltie and file in ManVal_PeakAreas.csv
  * Re-do Integragtion of peakareas
    


### 2018-10-15 - major update

*Quick fix*

Correction of file name after integration of incorporation data performed by MTXQCvX2_part3.

Issue: 
  * wrong file name pSIRM_Spectra_man.csv
  * correct: pSIRM_SpectraData_man.csv
  
Please download a new zip-file of MTXQCvX2!


### 2018-10-15 - minor update

I updated the error messages and actual catching errors related to ManualQuantTable.tsc-files. 

In detail MTXQCvX2_part1 checks now if you have renamed ManualQuantTable.tsv and if not, 
it exits the processing of your data. A related FATAL ERROR is shown in the pdf and directs
you what to do in order to solve this issue.

I hope it helps!



### 2018-10-08 - minor update

Update: 
  * Renaming of cinnamic acid related entries to internal standard
  * accordingly updated MTXQCvX_part1 and part2, as well as R functions
  * minor adjustments of plotting settings in MTXQCvX part2
  
### 2018-10-05 - major update

Update: 
  * Major corrections and modifications in MTXQCvX2 part 2
  * Restructure of internal R functions organisation
  * Integration of color styles


### 2018-09-27 - major update

comment: Please download a new copy of the MTXQCvX2

I updated the following:
  * MTXQCpart4: tracing empty data frames for internal standard
  * MTXQCpart1: tracing missing statistics: internal standard or sum of area
  * conversion_metabolite.csv: replaced value 99 in Mass_Pos

### 2018-09-25 - publication of repository

## Description
This current state includes fully automated Rmd-reports for Metabolomics projects.


## Technical details

### Input formats

Currenty supported input formats:
* Maui
* Metmax
* Spreadsheet (under dev)


## Implemented modules
### MTXQCinit

### MTXQC Experimental setup

Parameter of the report: 
* subfolder: text
* input: [metmax, maui]
* file annotation: e.g., annotation.csv
* sample extracts definition: e.g., Sample_extracts.csv
* kind of experiment: [qMTX, pSIRM, pSIRM timeseries]
* stable isotope: [none, glc, gln, pyr, other]
* InternalStandard: [none, cinnamicacid, other]
* origin: [blood, cell extracts, tissue, mixed]
* additional calibration: [no, yes]
* Quant-Mix: [Quant1_v3, Quant1_v4, Quant1_indv]
* Technical replicates: text

### MTXQC part1 - QC

Parameter of the report: 
* subfolder: 
* input: [metmax, maui]
* Manual Validation: [none, all, PeakAreas, Incorporation]
    
    
### MTXQC part2 - Post-Processing

Parameter of the report:
* subfolder:
* analysis: [stringent, less_stringent]
* InternalStandard: [True, False]
* Value of your choice: 
* Parameter 1: 
* Parameter 2: 
* Parameter 3:
* Parameter 4:
* Manual Validation: [none, all, PeakAreas, Incorporation]
    
### MTXQC part3 - Manual Validation

Parameter of the report:
* subfolder:
* output folder:
* transform: [none, PeakArea, Incorporation]
* integration: [none, PeakArea, Incorporation]
* input formatL: [metmax, maui]


### MTXQC part4 - Metmax integration

Parameter of the report: 
* subfolder: text
* PeakAreaMatrix: file-definition
* m73-data: file-defintion
* MIDs: file-definition
* InternalStandard: [True, False]
* Generate Alkane: [True, False]
* Generate SumOfArea-normalisation: [True, False]
* Generate ManualQuantTable and samples peakareamatrix: [True, False]
* Calculate incorporation: [True, False]


