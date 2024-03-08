# Project Title

## Summary

Provide a brief description of the project - 150 words.

## Highly Qualified Personnel

- Mireille Savoie, Mount Allison University, msavoie@mta.ca, ORCID 0009-0009-9499-6657
- Aurora Mattison, XXX institute, ajmattis@student.ubc.ca, XXX ORCID
- Julie Nadeau, Mount Allison University, janadeau@mta.ca,  ORCID 0009-0009-8123-6237
- Laurel Genge, XXX institute, XXX email, ORCID 0009-0006-7044-3394
- Maximilian Berthold, Mount Allison University, mberthold@mta.ca, ORCID 0000-0003-1985-6426
- Sylwia Śliwińska-Wilczewska, Mount Allison University, ssliwinskawilczews@mta.ca, ORCID 0000-0002-3147-6605
- Naaman M. Omar, Mount Allison University, nomar@mta.ca, ORCID 0000-0001-9583-2886
- Ondřej Prášil, Center Algatech, Laboratory of Photosynthesis, prasil@alga.cz, ORCID 0000-0002-0012-4359
- Amanda M. Cockshutt, St. Francis Xavier University, email XXX, ORCID 0000-0003-3024-2687

## Principal Investigators

- Douglas A. Campbell, Mount Allison University, dcampbel@mta.ca, ORCID 0000-0001-8996-5463

## Primary Contact  

- Douglas A. Campbell, Mount Allison University, dcampbel@mta.ca, ORCID 0000-0001-8996-5463
- Mireille Savoie, Mount Allison University, msavoie@mta.ca, ORCID 0009-0009-9499-6657


## Funding sources

- List your funding sources, grant names, and grant numbers as applicable.

## Keywords

Prochlorococcus, Oxygen, Photoperiod

## Additional information and support

- Sensitive Data Flag - Human Participants:  NO
- Sensitive Data Flag - Indigenous Partnerships: NO
- Sensitive Data Flag - Government Partnerships: NO
- Sensitive Data Flag - Industry Partnerships: NO
- Access Restrictions: NO

## Software  

The [@R-googlesheets4] package was used to read in the googlesheet 'MultiCultiCatalog' containing meta data. Data files (.csv) saved from the Multicultivator software, ascii (.asc) files from the Olis 14 UV/VIS Clarity Spectrophotometer and text (.txt) files from the Jaz spectrometer were imported into R (v4.1.3) and R-Studio (Posit Team, v2023.06.0) for data tidying and management using the [@R-tidyverse], [@R-data.table] and [@R-zoo] packages. Data analysis and visualization were done using the [@R-tidyverse], [@R-minpack.lm], [@R-mgcv], [@R-ggh4x], [@R-png], [@R-tagger], and [@R-kable] packages.  

## Repo content information

XXX DOI pending from BOREALIS? or DRYAD? XXX 

### MetaDataCatalog
URL for MultiCultiCatalog:
https://docs.google.com/spreadsheets/d/1ZXpwR7Gfto-uRzVdXzMpQF4frbrvMLH_IyLqonFZRSw/edit#gid=0


### Data Dictionary
Data Dictionary location and filename:
Docs/Prochlorococcus_O2_DataDictionary.csv

### Data/RawData

- CultureCatalog.Rds contains the meta data for the Multicultivator runs.
- JazEmData.zip folder has all .txt files containing emission spectra data of the Multicultivator LED lights.
- MultiCultiData1.zip, MultiCultiData2.zip and MultiCultiData3.zip folders has all .csv data files from the  Multicultivator. 
- OlisData.zip folder has all .asc files containing culture whole cell absorbance spectra data. 

### Data/ImportedData

-ImportedJazEmData folder contains "PICO_Imported_JazEmData.Rds" generated from Code/Import_JazEmData.Rmd
-ImportedMCData folder contains all "TargetFileName_TargetDataMetaFilter.Rds" files generated from Code/Import_MCData.Rmd
-ImportedOlisData folder contains "PICO_Imported_OlisData.Rds" generated from Code/Import_OlisData.Rmd

### Data/ProcessedData

-ProcessedMCData folder contains "TargetFileName_ProcessDataNestGrowth.Rds" generated from Code/Process_MCData.Rmd
-ProcessedOceanData folder contains "poi.RDS" generated from  XXXXX  and "pro_proteins.RDS" generated from  XXXXX 
-ProcessedOlisJazData folder contains "PICO_Processed_OlisJazMetaPUR.Rds" generated from Code/Process_OlisJazEmData.Rmd


### Data/CleanData

-CleanedMCData folder contains "PICO_Processed_MCGrowthFits.Rds" generated from Code/"Merge_MCGrowthData.Rmd"
-"PICO_Merged_GrowthFitsPURPAR.Rds" generated from Code/"Merge_GrowthPURData.Rmd"
-"ProchlorococcusEnzymeTable.Rds" generated from Code/"Plots_Genome.Rmd"   XXX Check thisXXX
-"ProchlorococcusGenomeData.Rds" generated from Code/"Plots_Genome.Rmd"   XXX Check thisXXX

Clean data in formats for long-term storage. Modified data with the appropriate column/row headers and data structure.



### Code

Scripts for processing raw data into cleaned data, outside derived code, and user derived code.
A folder OldR is used to store outdated code.
Typically organize .Rmd in modules; Import; Tidy; Process saving .Rds out of each step.

### Docs

Project notes, other documentation, etc.

### Output

Output from knit .Rmd, Figures and tables produced from analysis.
Do not generate swarms of superfluous data exploration figures.
