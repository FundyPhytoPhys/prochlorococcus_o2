# Code

#### Import_MetaData.Rmd

Imports metadata for Multicultivator experiments. Metadata URL location:
https://docs.google.com/spreadsheets/d/1ZXpwR7Gfto-uRzVdXzMpQF4frbrvMLH_IyLqonFZRSw/edit#gid=0

#### Import_MCData.Rmd

This script imports and tidies Muticultivator data in simple .csv long form (Data/RawData/MultiCultiData.zip/"yyyymmdd_PICO_MCXXXXXX_RUNXXX.csv") based upon project specific values for variables
set by the user. Multicultivator data files are too large to upload in a single .zip folder therefore 3 .zipped folders ("MultiCultiData1.zip", "MultiCultiData2.zip" and "MultiCultiData3.zip") are uploaded. Uncomment the 'DataIn' line with the folder name containing the intended files for import. Individual multicultivator runs are imported and tidied one at a time. A metadata catalog (Data/RawData/"CultureCatalog.Rds") is imported and merges with the imported data based
upon shared values for the variables 'MC', 'Tube', and 'Filename' which unambiguously identify a given growth trajectory measured at OD680 or OD720. Each individually imported and tidied multicultivator run is saved as a .Rds in the "Data/ImportedData/ImportedMCData" folder as "yyyymmdd_PICO_MCXXXXXX_RUNXXX_TargetDataMetaFilter.Rds" for further processing in "Code/Process_MCData.Rmd". 

#### Process_MCData.Rmd

This script reads in individually tidied Muticultivator runs from "Data/ImportedData/ImportedMCData" folder and implements logistic and other growth curve fits to the MultiCultivator growth trajectories. The processed .Rds are saved in the "Data/ProcessedData/ProcessedMCData" folder as "yyyymmdd_PICO_MCXXXXXX_RUNXXX_ProcessDataNestGrowth.Rds" for further processing in "Code/Merge_MCGrowthData.Rmd".


#### Merge_MCGrowthData.Rmd

This script reads in all individually processed Muticultivator runs containing growth fits from the "/Data/ProcessedData/ProcessedMCData" folder and merges the data into 1 data frame. This single data frame is saved as a .Rds called "PICO_Processed_MCGrowthFits.Rds" in the "/Data/CleanData/CleanedMCData" folder to be merged later with PUR data using the "Merge_GrowthPURData.Rmd" script.


#### Import_JazEmData.Rmd

This script imports and tidies all Jaz spectrometer emission files (.txt) from "Data/RawData/JazEmData.zip". The tidied data of all the emission spectra is saved as one .Rds named "PICO_Imported_JazEmData.Rds" in the "Data/ImportedData/ImportedJazEmData" folder for further analysis in "Process_OlisJazEmData.Rmd".


#### Import_OlisData.Rmd

This script imports and tidies all OLIS 14 UV/VIS Clarity spectrophotometer whole cell absorbance files (.asc) from "Data/RawData/OlisData.zip". The tidied data of all the absorbance spectra is saved as one .Rds named "PICO_Imported_OlisData.Rds" in the "Data/ImportedData/ImportedOlisData" folder for further analysis in "Process_OlisJazEmData.Rmd".


#### Process_OlisJazEmData.Rmd

This script imports, merges and calculates the Photosynthetically Usuable Radiation (PUR) from the "PICO_Imported_JazEmData.Rds" and the "PICO_Imported_OlisData.Rds" files.  The tidied data of all the PUR, absorbance and emission spectra is saved as one .Rds named "PICO_Processed_OlisJazMetaPUR.Rds" in the "Data/ImportedData/ImportedJazEmData" folder to be merged with growth data using the "Merge_GrowthPURData.Rmd" script. 


#### Merge_GrowthPURData.Rmd

This script imports and merges the "PICO_Processed_MCGrowthFits.Rds" and "PICO_Processed_OlisJazMetaPUR.Rds" and assigns Photosynthetically Usuable Radiation (PUR) from the calculated PUR results in "PICO_Processed_OlisJazMetaPUR.Rds" to the appropriate matching PAR and WL for each strain in the "PICO_Processed_MCGrowthFits.Rds". The tidied data of all the growth rate  estimates, PUR, PAR and nested data frames containing whole cell absorbance and emission spectra and Multicultivator OD measurements for every combination of the growth matrix experiments is saved as "PICO_Merged_GrowthFitsPURPAR.Rds" in the "Data/CleanData" folder and used to generate statistics and figures using "Plots_GAM.Rmd" and "Plots_PURFits.Rmd" and figures using "Plots_Growth.Rmd".

#### Plots_GAM.Rmd

This .Rmd reads in "PICO_Merged_GrowthFitsPURPAR.Rds" from the "Data/CleanData" folder and produces a Generalized Additive Model (GAM) to examine the relationship between the chlorophyll proxy (ΔOD) growth rate across the blue and red spectral wavebands, photoperiod and PAR levels for each *P.marinus* ecotype in this study. The GAM function from the R package mgcv (Wood, 2022) was used to model the growth rate with smoothing terms to indicate the 90, 50 and 10% quantiles. The generated GAM plots ("MED4PARGAM.png", "SS120PARGAM.png" and "MIT9313PARGAM.png") are saved in the "Output/Figures" folder and later read into "Manuscript_O2.Rmd".

#### Plots_Growth.Rmd

This .Rmd reads in "PICO_Merged_GrowthFitsPURPAR.Rds" from the "Data/CleanData" folder and generates figures that are later called into "Manuscript_O2.Rmd". The generated plots ("PurParPlot.png","OverlayPlots.png" and "deltaODLogGrowthPlot.png") are saved in the "Output/Figures" folder. 


#### Plots_PURFits.Rmd

This .Rmd reads in "PICO_Merged_GrowthFitsPURPAR.Rds" from the "Data/CleanData" folder and generates a one-way ANOVA to examine statistical differences between Harrison and Platt four parameter model fit to 660 nm (red light) and 450 nm (blue light) growth data for each combination of strain and [O~2~]. Additionally, a one-way ANOVA was used to examine statistical differences between Harrison and Platt four parameter model fit to each photoperiod (4 h, 8 h, 12 h, 16 h) and pooled photoperiod growth data for each combination of strain and [O~2~]. Photoperiod growth data that showed complete growth inhibition for each combination of strain, [O~2~] and imposed spectral waveband were omitted from the pooled photoperiod model. Statistical differences were determined at P value < 0.05. It can be safely assumed that *P.marinus* dies at PAR of 0 µE therefore, dummy values of no growth (µ = 0) for dark conditions were assigned for each combination of [O~2~], photoperiod and spectral waveband for each strain to anchor the starting point of the model. The generated PUR fit plots ("BluevsRedPurFitsPlots.png" and "PhotoperiodPurFitsPlots.png") are saved in the "Output/Figures" folder and later read into "Manuscript_O2.Rmd". 

#### Plots_Genome.Rmd

This .Rmd reads in "ProchlorococcusGenomeData.Rds" from the "Data/CleanData" folder.
The generated plots ("ProchlorococcusEnzymeKms.png", "DNARepairFig.png" and "ProchlorococcusLightEnzymesFig.png") are saved in the "Output/Figures" folder and later read into "Manuscript_O2.Rmd".


#### Plots_OceanProtein.Rmd

This .Rmd reads in "poi.RDS" from the "Data/ProcessedData/ProcessedOceanProtein" folder and generates figures that are later called into "Manuscript_O2.Rmd". The generated plots ("CladeProchloroPhotosynthDepthO2.png" and "CladeProchloroProteinMetabDepthO2.png") are saved in the "Output/Figures" folder.

#### Plots_ProNicheMap.Rmd

This .Rmd reads in "DepthPhotoperiodTableFilter.Rds" from the "Data/ProcessedData" folder and generates figure "Output/Figures/NichesMap.png"" that is later called into "Manuscript_O2.Rmd".


#### Manuscript_O2.Rmd

This .Rmd uses R Markdown and knits to .docx and html to produce a manuscript style document formatted for PLOS ONE publication.  The .Rmd reads in "PICO_Merged_GrowthFitsPURPAR.Rds" from the "Data/CleanData" folder and generates a table of maximum growth rate for each strain grown under each [O~2~] condition. Figures are read in from the "Output/Figures" folder. The Word and html documents are saved as "Manuscript_O2.docx" and "Manuscript_O2.html" in the "Code" folder.

#### KnitTemplate.docx

This is the template used to format the knitted WORD document.

#### scholarly-metadata.lua and author-info-blocks.lua

These are required files to format the authorship and affiliations properly when knitting to html and Word.

#### _bookdown.yml

This file overwrites the bookdown default settings in the yaml and allows the knitted .docx and html to be saved in the "Output" folder.
