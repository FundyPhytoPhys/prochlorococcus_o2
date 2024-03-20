# Project Title

## Summary

Provide a brief description of the project - 150 words.

## Highly Qualified Personnel

- Mireille Savoie, Mount Allison University, msavoie@mta.ca, ORCID 0009-0009-9499-6657
- Aurora Mattison, University of British Columbia, ajmattis@student.ubc.ca, XXX ORCID
- Laurel Genge, Fisheries and Oceans Canada, laurel-maud@hotmail.com, ORCID 0009-0006-7044-3394
- Julie Nadeau, Mount Allison University, janadeau@mta.ca,  ORCID 0009-0009-8123-6237
- Maximilian Berthold, Mount Allison University, mberthold@mta.ca, ORCID 0000-0003-1985-6426
- Sylwia Śliwińska-Wilczewska, Mount Allison University, ssliwinskawilczews@mta.ca, ORCID 0000-0002-3147-6605
- Naaman M. Omar, Mount Allison University, nomar@mta.ca, ORCID 0000-0001-9583-2886
- Ondřej Prášil, Center Algatech, Laboratory of Photosynthesis, prasil@alga.cz, ORCID 0000-0002-0012-4359
- Amanda M. Cockshutt, St. Francis Xavier University, acockshu@stfx.ca, ORCID 0000-0003-3024-2687

## Principal Investigators

- Douglas A. Campbell, Mount Allison University, dcampbel@mta.ca, ORCID 0000-0001-8996-5463

## Primary Contact  

- Douglas A. Campbell, Mount Allison University, dcampbel@mta.ca, ORCID 0000-0001-8996-5463
- Mireille Savoie, Mount Allison University, msavoie@mta.ca, ORCID 0009-0009-9499-6657


## Funding sources

- Canada Research Chair in Phytoplankton Ecophysiology (DAC), Grant number CRC-2017-00075
- Natural Sciences and Engineering Research Council of Canada, 'Latitude and Light' (DAC)
- Canada Foundation for Innovation (DAC) 
- New Brunswick Foundation for Innovation (DAC and MS) 
- Rice Graduate Fellowship 2021 and 2022 (MS)
- Czech Academy of Science (OP) visiting fellowship supporting DAC work at AlgaTech 

## Keywords

*Prochlorococcus*, Oxygen, Photoperiod

## Additional information and support

- Sensitive Data Flag - Human Participants:  NO
- Sensitive Data Flag - Indigenous Partnerships: NO
- Sensitive Data Flag - Government Partnerships: NO
- Sensitive Data Flag - Industry Partnerships: NO
- Access Restrictions: NO

## Software  

Data was imported and tidied into R (v4.1.3), running under R-studio (Posit Team, v2023.06.0), using the 'tidyverse' [@R-tidyverse], 'glue' [@R-glue], 'ggh4x' [@R-ggh4x], 'ggtext' [@R-ggtext], 'ggpubr' [@R-ggpubr], 'minpack.lm' [@R-minpack.lm], [@R-data.table], [@R-zoo], [@R-mgcv], [@R-kable] and 'nlstools' [@R-nlstools] packages. Formatted outputs were generated from Rmarkdown files using the 'knitr' [@R-knitr] and 'bookdown' [@R-bookdown] packages. The 'MultiCultiCatalog' googlesheet containing metadata was read using the [@R-googlesheets4] package. 

## Repo content information

### MetaDataCatalog

https://docs.google.com/spreadsheets/d/1ZXpwR7Gfto-uRzVdXzMpQF4frbrvMLH_IyLqonFZRSw/edit#gid=0


### Data Dictionary

Data Dictionary can be found in "Docs/Prochlorococcus_O2_DataDictionary.csv"

### Data/RawData

- CultureCatalog.Rds contains the metadata for Multicultivator runs generated from "Code/Import_MetaData.Rmd".
- MultiCultiData1.zip, MultiCultiData2.zip and MultiCultiData3.zip folders has all .csv data files from the Multicultivators. 
- JazEmData.zip folder has all .txt files containing emission spectra data of the Multicultivator LED lights.
- OlisData.zip folder has all .asc files containing culture whole cell absorbance spectra data from the Olis Clarity. 

### Data/ImportedData

- ImportedJazEmData folder contains "PICO_Imported_JazEmData.Rds" generated from "Code/Import_JazEmData.Rmd"
- ImportedMCData folder contains all "TargetFileName_TargetDataMetaFilter.Rds" files generated from "Code/Import_MCData.Rmd"
- ImportedOlisData folder contains "PICO_Imported_OlisData.Rds" generated from "Code/Import_OlisData.Rmd"

### Data/ProcessedData

- ProcessedMCData folder contains "TargetFileName_ProcessDataNestGrowth.Rds" generated from Code/Process_MCData.Rmd
- ProcessedOceanData folder contains "poi.RDS" generated from  XXXXX  and "pro_proteins.RDS" generated from  XXXXX 
- ProcessedOlisJazData folder contains "PICO_Processed_OlisJazMetaPUR.Rds" generated from Code/Process_OlisJazEmData.Rmd


### Data/CleanData

- CleanedMCData folder contains "PICO_Processed_MCGrowthFits.Rds" generated from Code/"Merge_MCGrowthData.Rmd"
- "PICO_Merged_GrowthFitsPURPAR.Rds" generated from Code/"Merge_GrowthPURData.Rmd"
- "ProchlorococcusEnzymeTable.Rds" generated from Code/"XXXXX.Rmd"   XXX Check thisXXX
- "ProchlorococcusGenomeData.Rds" generated from Code/"XXXXX.Rmd"   XXX Check thisXXX


### Code




### Docs

- "Prochlorococcus_O2_DataDictionary.csv" is the data dictionary 
- "PLOSONE_CoverLetter.docx" is the cover letter to PLOS ONE

### Output

Figures generated using Code/"Plots_Growth.Rmd":
- "MED4PAR.png", "SS120PAR.png", "MIT9313PAR.png", 
"PurParPlot.png", "deltaODLogGrowthPlot.png"

Figures generated using Code/"Plots_GAM.Rmd":
- "MED4GAM.png", "SS120GAM.png", "MIT9313GAM.png"

Figures generated using Code/"Plots_PURfits.Rmd":
- "BluevsRedPurFitsPlots.png", "PhotoperiodPurFitsPlots.png"

Figures generated using Code/"Plots_Genome.Rmd":
- "DNARepairFig.png", "ProchlorococcusEnzymeKms.png", "ProchlorococcusLightEnzymes.png"

Figures generated using Code/"Plots_OceanProtein.Rmd":
- "CladeProchloroPhotosynthDepthO2.png", "CladeProchloroProteinMetabDepthO2.png"

The editable Powerpoint file named "LabeledMC.pptx" was used to generated the labeled Multicultivator picture named "LabeledMC.png".
