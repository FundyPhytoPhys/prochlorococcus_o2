# Project Title

## Summary

*Prochlorococcus marinus*, the smallest picocyanobacterium, comprises
multiple clades with distinct niches across tropical and sub-tropical
oligotrophic ocean regions, including Oxygen Minimum Zones. Ocean
warming may open permissive temperatures in new, poleward photic
regimes, along with expanded Oxygen Minimum Zones. We used ocean protein
data to help guide testing of
*Prochlorococcus marinus* growth across a matrix of peak irradiances,
photoperiods, spectral bands and dissolved oxygen. MED4 from Clade HLI
requires greater than 4 h photoperiod, grows at 25 µmol O~2~ L^-1^ and
above, and exploits high cumulative diel photon doses, yet shows
accelerated growth when the cost of photoinactivation is lowered under
red, vs. blue, actinic light. MED4 relies upon an alternative oxidase to
balance electron transport, which may exclude it from growth under our
lowest, 2.5 µmol O~2~ L^-1^, condition. SS120 from Clade LLII/III is
restricted to low light under full 250 µmol O~2~ L^-1^, shows expanded
light exploitation under 25 µmol O~2~ L^-1^, but is excluded from growth
under 2.5 µmol O~2~ L^-1^. Intermediate oxygen suppresses the cost of
PSII photoinactivation, and enzymatic production of H~2~O~2~ in SS120,
which has limited genomic capacity for PSII and DNA repair. MIT9313 from
Clade LLIV is restricted to low blue irradiance under 250 µmol O~2~
L^-1^, but exploits much higher irradiance under red light, or under
lower O~2~ concentrations, conditions which slow photoinactivation of
PSII and production of reactive oxygen species.

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

The metadata for Multicultivator runs is generated from "Code/Import_MetaData.Rmd" which calls in the googlesheet: https://docs.google.com/spreadsheets/d/1ZXpwR7Gfto-uRzVdXzMpQF4frbrvMLH_IyLqonFZRSw/edit#gid=0


### Data Dictionary

Data Dictionary can be found in "Docs/prochlorococcus_O2_DataDictionary.csv"

### Code folder

#### Import_MetaData.Rmd

Imports metadata for Multicultivator experiments. Metadata URL location:
https://docs.google.com/spreadsheets/d/1ZXpwR7Gfto-uRzVdXzMpQF4frbrvMLH_IyLqonFZRSw/edit#gid=0 and outputs "CultureCatalog.Rds"

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

This .Rmd reads in "PICO_Merged_GrowthFitsPURPAR.Rds" from the "Data/CleanData" folder and generates figures that are later called into "Manuscript_O2.Rmd". The generated plots ("PurParPlot.png", "MED4PAR", "SS120PAR", "MIT9313PAR", "OverlayPlots.png" and "deltaODLogGrowthPlot.png") are saved in the "Output/Figures" folder. 


#### Plots_PURFits.Rmd

This .Rmd reads in "PICO_Merged_GrowthFitsPURPAR.Rds" from the "Data/CleanData" folder and generates a one-way ANOVA to examine statistical differences between Harrison and Platt four parameter model fit to 660 nm (red light) and 450 nm (blue light) growth data for each combination of strain and [O~2~]. Additionally, a one-way ANOVA was used to examine statistical differences between Harrison and Platt four parameter model fit to each photoperiod (4 h, 8 h, 12 h, 16 h) and pooled photoperiod growth data for each combination of strain and [O~2~]. Photoperiod growth data that showed complete growth inhibition for each combination of strain, [O~2~] and imposed spectral waveband were omitted from the pooled photoperiod model. Statistical differences were determined at P value < 0.05. Dummy values of no growth (µ = 0) for dark conditions at PAR of 0 µE were assigned for each combination of [O~2~], photoperiod and spectral waveband for each strain to anchor the starting point of the model. The generated PUR fit plots ("BluevsRedPurFitsPlots.png" and "PhotoperiodPurFitsPlots.png") are saved in the "Output/Figures" folder and later read into "Manuscript_O2.Rmd". 

#### Plots_Genome.Rmd

This .Rmd reads in "ProchlorococcusGenomeData.Rds" from the "Data/CleanData" folder.
The generated plots ("ProchlorococcusEnzymeKms.png", "DNARepairFig.png" and "ProchlorococcusLightEnzymesFig.png") are saved in the "Output/Figures" folder and later read into "Manuscript_O2.Rmd".


#### Plots_OceanProtein.Rmd

This .Rmd reads in "poi.RDS" from the "Data/ProcessedData/ProcessedOceanProtein" folder and generates figures that are later called into "Manuscript_O2.Rmd". The generated plots ("CladeProchloroPhotosynthDepthO2.png" and "CladeProchloroProteinMetabDepthO2.png") are saved in the "Output/Figures" folder.

#### Plots_ProNicheMap.Rmd

This .Rmd reads in "DepthPhotoperiodTableFilter.Rds" from the "Data/ProcessedData" folder and generates figure 'Output/Figures/NicheMap.png' that is later called into "Manuscript_O2.Rmd".



#### Manuscript_O2.Rmd

This .Rmd uses R Markdown and knits to .docx and html to produce a manuscript style document formatted for PLOS ONE publication.  The .Rmd reads in "PICO_Merged_GrowthFitsPURPAR.Rds" from the "Data/CleanData" folder and generates a table of maximum growth rate for each strain grown under each [O~2~] condition. Figures are read in from the "Output/Figures" folder. The Word and html documents are saved as "Manuscript_O2.docx" and "Manuscript_O2.html" in the "Code" folder.

#### KnitTemplate.docx

This is the template used to format the knitted WORD document.

#### scholarly-metadata.lua and author-info-blocks.lua

These are required files to format the authorship and affiliations properly when knitting to html and Word.

#### _bookdown.yml

This file overwrites the bookdown default settings in the yaml and allows the knitted .docx and html to be saved in the "Output" folder.

### Data folder

#### CleanData subfolder

- "CleanedMCData" subfolder contains "PICO_Processed_MCGrowthFits.Rds" generated from "Code/Merge_MCGrowthData.Rmd"
- "PICO_Merged_GrowthFitsPURPAR.Rds" generated from "Code/Merge_GrowthPURData.Rmd"
- "ProchlorococcusEnzymeTable.Rds" generated from "Code/XXXXX.Rmd"   XXX Check thisXXX
- "ProchlorococcusGenomeData.Rds" generated from "Code/XXXXX.Rmd"   XXX Check thisXXX

#### ImportedData subfolder

- "ImportedJazEmData" subfolder contains "PICO_Imported_JazEmData.Rds" generated from "Code/Import_JazEmData.Rmd"
- "ImportedMCData" subfolder contains all "TargetFileName_TargetDataMetaFilter.Rds" files generated from "Code/Import_MCData.Rmd"
- "ImportedOlisData" subfolder contains "PICO_Imported_OlisData.Rds" generated from "Code/Import_OlisData.Rmd"

#### ProcessedData subfolder

- "ProcessedMCData" subfolder contains "TargetFileName_ProcessDataNestGrowth.Rds" generated from "Code/Process_MCData.Rmd"
- "ProcessedOceanData" subfolder contains "poi.RDS" generated from  XXXXX  and "pro_proteins.RDS" generated from  XXXXX 
- "ProcessedOlisJazData" subfolder contains "PICO_Processed_OlisJazMetaPUR.Rds" generated from "Code/Process_OlisJazEmData.Rmd"

#### RawData subfolder

- "CultureCatalog.Rds" contains the metadata for Multicultivator runs generated from "Code/Import_MetaData.Rmd".
- "MultiCultiData1.zip", "MultiCultiData2.zip" and "MultiCultiData3.zip" subfolders contain all .csv data files from the Multicultivators. 
- "JazEmData.zip" subfolder has all .txt files containing emission spectra data of the Multicultivator LED lights.
- "OlisData.zip" subfolder has all .asc files containing culture whole cell absorbance spectra data from the Olis Clarity. 

### Docs folder

- "prochlorococcus_O2_DataDictionary.csv" is the data dictionary. 
- "PLOSONE_CoverLetter.docx" is the cover letter to PLOS ONE.
- "plos-one.csl" is the citation style language for PLOS ONE used in "Manuscript_O2.Rmd".
- "RPackages.bib" is the bibliography for R packages citations used in "Manuscript_O2.Rmd".
- "Manuscript_O2.bib" is the bibliography for citations used in "Manuscript_O2.Rmd".
- "FaultyCitations.bib" is the bibliography containing user generated citation keys used in "Manuscript_O2.Rmd"

### Output folder

#### Figures subfolder

Figures generated using "Code/Plots_Growth.Rmd":
- "PurParPlot.png", "deltaODLogGrowthPlot.png", "OverlayPlots.png"

Figures generated using "Code/Plots_GAM.Rmd":
- "MED4PARGAM.png", "SS120PARGAM.png", "MIT9313PARGAM.png"

Figures generated using "Code/Plots_PURfits.Rmd":
- "BluevsRedPurFitsPlots.png", "PhotoperiodPurFitsPlots.png"

Figures generated using "Code/Plots_Genome.Rmd":
- "DNARepairFig.png", "ProchlorococcusEnzymeKms.png", "ProchlorococcusLightEnzymes.png"

Figures generated using "Code/Plots_OceanProtein.Rmd":
- "CladeProchloroPhotosynthDepthO2.png", "CladeProchloroProteinMetabDepthO2.png"

Figure generated using "Code/Plots_ProNicheMap.Rmd":
- "NichesMap.png"

The editable Powerpoint file named "LabeledMC.pptx" was used to generated the labeled Multicultivator picture named "LabeledMC.png".

#### PLOSRound1 subfolder

Contains all .tiff figures renamed to match the order in which they appear in the manuscript (Fig1 to Fig12) and "Manuscript_O2_PLOS1.docx" is the manuscript formatted as per PLOS ONE guideline for submission.  

#### PLOSRound2 subfolder

Contains all .tiff figures renamed to match the order in which they appear in the manuscript and "Manuscript_O2_PLOS2.docx" is the manuscript formatted as per PLOS ONE guideline for submission.  