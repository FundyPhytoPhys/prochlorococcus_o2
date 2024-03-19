# Code

#### Import_MetaData.Rmd

Imports metadata for Multicultivator experiments. Metadata URL location:
https://docs.google.com/spreadsheets/d/1ZXpwR7Gfto-uRzVdXzMpQF4frbrvMLH_IyLqonFZRSw/edit#gid=0

#### Import_MCData.Rmd

This script imports and tidies Muticultivator data in simple .csv long form (Data/RawData/MultiCultiData.zip/"yyyymmdd_PICO_MCXXXXXX_RUNXXX.csv") based upon project specific values for variables
set by the user. Multicultivator data files are too large to upload in a single .zip folder therefore 3 .zipped folders ("MultiCultiData1.zip", "MultiCultiData2.zip" and "MultiCultiData3.zip") are uploaded. Uncomment the 'DataIn' line with the folder name containing the intended files for import. Individual multicultivator runs are imported and tidied one at a time. A metadata catalog (Data/RawData/"CultureCatalog.Rds") is imported and merges with the imported data based
upon shared values for the variables 'MC', 'Tube', and 'Filename' which unambiguously identify a given growth trajectory measured at OD680 or OD720. Each individually imported and tidied multicultivator run is saved as a .Rds in the "Data/ImportedData/ImportedMCData" folder as "yyyymmdd_PICO_MCXXXXXX_RUNXXX_TargetDataMetaFilter.Rds" for further processing in "Code/Process_MCData.Rmd". 

#### Process_MCData.Rmd

This script reads in individually tidied Muticultivator runs from "Data/ImportedData/ImportedMCData" folder and implements logistic and other growth curve fits to the MultiCultivator growth trajectories. The processed .Rds are saved in the "Data/ProcessedData/ProcessedMCData" folder as "yyyymmdd_PICO_MCXXXXXX_RUNXXX_ProcessDataNestGrowth.Rds" for further manipulation in "Code/Merge_MCGrowthData.Rmd".


#### Merge_MCGrowthData.Rmd

This script reads in all individually processed Muticultivator runs containing growth fits from the "/Data/ProcessedData/ProcessedMCData" folder and merges the data into 1 data frame. This single data frame is saved as a .Rds called "PICO_Processed_MCGrowthFits.Rds" in the "/Data/CleanData/CleanedMCData" folder to be merged later with PUR data using the "Merge_GrowthPURData.Rmd" script.


#### Import_JazEmData.Rmd

This script imports and tidies all Jaz spectrometer emission files (.txt) from "Data/RawData/JazEmData.zip". The tidied data of all the emission spectra are saved as one .Rds named "PICO_Imported_JazEmData.Rds".  in "Data/ImportedData/ImportedJazEmData" folder as  for further analysis in "Process_OlisJazEmData.Rmd".


#### Import_OlisData.Rmd

This script imports OLIS 14 UV/VIS Clarity spectrophotometer whole cell absorbance files (.asc) from "Data/RawData/OlisData.zip" folder and stored in Data/ImportedData/ImportedOlisData folder as: 
PICO_Imported_OlisData.Rds

#### Process_OlisJazEmData.Rmd

#### Merge_GrowthPURData.Rmd

#### PICOgam.Rmd 

This .Rmd produces a Generalized Additive Model (GAM) to examine the relationship between the chlorophyll proxy (ΔOD) growth rate across the blue and red spectral wavebands, photoperiod and PAR levels for each P.marinus ecotype in this study. The gam function from the R package mgcv (Wood, 2022) was used to model the growth rate with smoothing terms to indicate the 90, 50 and 10% quantiles. "PICO_Merged_GrowthFitsPURPAR.Rds" is called in from /Data/CleanData/CleanedMCData folder and generated GAM plots are saved in /Output/Figures folder as .png.

#### ManuscriptFigures.Rmd

