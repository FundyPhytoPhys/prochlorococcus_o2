---
title: "Functional Analyses of Distinct Oxygen Concentrations and Light Niches of *Prochlorococcus marinus*"
author:
  - name: '**Mireille Savoie**'
    affil: 1
    main: true
    email: msavoie@mta.ca
  - name: Julie Nadeau
    affil: 1
  - name: Laurel Genge
    affil: 1
  - name: Sylwia Śliwińska-Wilczewska
    affil: 1,2
  - name: Maximilian Berthold
    affil: 1
  - name: Naaman Omar
    affil: 1
  - name: Douglas A. Campbell
    affil: 1
    main: false
    orcid: ''
    email: 'dcampbel@mta.ca'
affiliation:
  - num: 1
    address: Department of Biology, Mount Allison University
institute:
  - mta: 'Department of Biology, Mount Allison University, 53 York St., Sackville NB, Canada, E4L 1C9.'
date: "2024-01-18"
output:
  bookdown::html_document2:
    code_folding: show
    keep_md: yes
    toc: TRUE
    toc_float: TRUE
    toc_depth: 6
    fig_caption: yes
    pandoc_args: 
      - '--lua-filter=scholarly-metadata.lua'
      - '--lua-filter=author-info-blocks.lua'
  bookdown::word_document2:
    code_folding: show
    reference_docx: KnitTemplate.docx
    keep_md: yes
    toc: TRUE
    toc_depth: 6
    fig_caption: yes
    pandoc_args: 
      - '--lua-filter=scholarly-metadata.lua'
      - '--lua-filter=author-info-blocks.lua'
always_allow_html: true
bibliography: [Manuscript_O2.bib, RPackages.bib]
csl: plos-one.csl
editor_options: 
  markdown: 
    wrap: 72
---

<style type="text/css">
p.caption {
  font-size: 12px;
}
</style>











# Abstract {.unnumbered}


\newpage

# Introduction {.unnumbered}




\newpage

# Materials and methods {.unnumbered}

## Culturing {.unnumbered}

%%%%%% Taken from my thesis word for word, need to reword and shorten %%%%

Three xenic *P. marinus* cultures, obtained from Bigelow Labs, NCMA
Maine, US: MED4 (CCMP1986) from a High Light-adapted (HLI) clade, SS120
(CCMP1375) from a Low Light-adapted (LLIII) clade and MIT9313 (CCMP2773)
also from a Low Light-adapted (LLIV) clade. These cultures were then
maintained in two separate incubators. The temperature for both
incubators was set to 22°C and a light/dark cycle of 12 h. The PAR level
of the incubator was chosen to reflect the light level of the natural
niche of the ecotype during culturation. The PAR level of the incubator
containing the HLI clade, MED4, was set at 160 µmol photons m^-2^ s^-1^,
whereas the incubator containing the LLIII and LLIV clades, SS120 and
MIT9313 respectively, was set at 30 µmol photons m^-2^ s^-1^. To ensure
cultures remained in exponential growth phase, all strains were
transferred weekly in Pro99 media prepared according to
[@mooreCulturingMarineCyanobacterium2007] in autoclaved artificial
seawater. Artificial seawater was prepared according to the National
Center for Marine Algae and Microbiota (NCMA) protocol by combining salt
solution I and salt solution II using the enriched artificial seawater
(ESAW) recipe.

## Experimental design {.unnumbered}

%%%%%% Taken from my thesis word for word, need to reword and shorten %%%%

For each of three ecotypes, we imposed [O~2~] (three levels: 2.5 µM,
25µM, 250 µM), photoperiod (four levels: 4 h, 8 h, 12 h, 16 h), spectral
waveband (four bands: full spectrum white LED, 660 nm, 530 nm, 450 nm),
and light level (three levels: 30, 90, 180 µmol photons m^-2^ s^-1^)
treatments in a factorial design. Each factor is explained below. The
full crossing of all factors would yield 3 x 4 x 4 x 3 = 144 treatments
per ecotype (432 total), but due to time constraints and total absence
of growth of some ecotypes under some conditions, not all treatments
were carried out. In total, we completed 291 treatments.

All growth experiments were conducted at 22°C.

## Experimental light conditions {.unnumbered}

%%%%%% Taken from my thesis word for word, need to reword and shorten %%%%

Three growth Photosynthetically Active Radiation (PAR) levels (180, 90,
and 30 µmol photons m^-2^ s^-1^) and four spectral wavebands (white LED
full spectrum, 660 nm, 530 nm, and 450 nm) were chosen to simulate light
levels and spectral color spanning the vertical ocean water column, from
near-surface to the lower euphotic zone depths (Figure
\@ref(fig:SunDepth)). For simplicity, actinic light used for growth
under specific wavebands will be referred by the respective spectral
color; white LED for LED full spectrum, red for 660 nm, green for 530 nm
and blue for 450 nm. Four different photoperiods were chosen to simulate
various diel cycles characteristic of current and hypothetical future
niches of *P. marinus*. A photoperiod of 16 h was chosen to represent
temperate (45°N) summer at the ocean surface, 12 h for equatorial (0°N)
ocean surface or temperate (45°N) spring and fall ocean surface or
temperate (45°N) summer at deep ocean depths, 8 h for temperate (45°N)
winter at the surface or at temperate (45°N) spring and fall at depth
and equatorial (0°N) deep ocean depths and 4 h for temperate (45°N)
winter or deep ocean depths during temperate (45°N) spring and fall.

## Experimental oxygen conditions {.unnumbered}

%%%%%% Taken from my thesis word for word, need to reword and shorten %%%%

Three target dissolved oxygen concentrations [O~2~] were delivered to
tubes of the Multicultivator by mixing varying ratios of air and
Nitrogen (N~2~) gases while delivering 0.05% of Carbon Dioxide (CO~2~)
gas through a 0.2 μm sterile microfilter via a G400 gas mixing system.
To confirm and monitor the [O~2~], 4 FireSting optodes (PyroScience,
Germany) were inserted into select tubes of each modified [O~2~] run for
real-time measurements. A compensation temperature probe was placed in
the aquarium of the bioreactor to correct [O~2~] for temperature
fluctuations. In addition, the software corrected [O~2~] based on the
salinity of the media (32 ppt). For the low O~2~ environment
experiments, 0.5 to 1.0 µM of O~2~ was delivered to each Multicultivator
tube by sparging with a gas mixture containing 99.95% N~2~ and 0.05%
CO~2~ to purge dissolved O~2~ out of the culture. The intermediate O~2~
environment experiments were sparged to deliver 10 to 25 µM of O~2~
using a gas mixture containing 98.95% N~2~, 0.05% CO~2~ and 1% O~2~. The
high O~2~ environment experiments were sparged with lab air (78% N~2~,
21% O~2~, 1% Ar and 0.05% CO~2~) to deliver 230 µM of O~2~. While the
flow rate of the gas mixture was controlled, variations in bubbling
speed affected the [O~2~] delivered to each tube; therefore, a range of
[O~2~] was defined for each experimental O~2~ level; 0.5 µM - 5 µM for
low, 5 µM - 50 µM for intermediate and 200 µM - 280 µM for high O~2~
experiments. To simplify the representation of experimental [O~2~]
conditions in graphs and discussions, the approximate median [O~2~] of
each experimental range: 2.5 µM, 25 µM, and 250 µM, will be used for
low, intermediate, and high conditions, respectively. Figure
\@ref(fig:O2DataCapture) shows the data capture software of the
FireSting Oxygen Logger. Dissolved [O~2~] were measured every 5 minutes
over the duration of the Multicultivator run and recorded in a text file
for later processing in R-Studio (Figure \@ref(fig:O2Plot)).

\newpage

## Bioreactors {.unnumbered}

%%%%%% Taken from my thesis word for word, need to reword and shorten %%%%


Growth experiments under different spectral wavebands were performed
using a PSI MCMIX-OD Multicultivator (Figure \@ref(fig:MCpicture)) or a
PSI MC1000-OD Multicultivator for white LED experiments. Each
Multicultivator has the capacity to individually control 8 tubes with
specific PAR levels and photoperiods and the MCMIX-OD has options for
individually controlled spectral wavebands. 10 mL of exponential growth
culture was added to 70 mL of Pro99 media and all 8 tubes were situated
in a common temperature-controlled water bath to ensure the temperature
remained constant at 22°C over the duration of the experiment. Real time
absorbance measurements of Optical Density (OD) 680 nm (a proxy for cell
suspension density, cell scatter and cell chlorophyll content) and OD
720 nm (a proxy for cell suspension density and cell scatter) were
recorded every 5 minutes for at least 8 to 14 days depending on the
duration of the lag phase, if any. Figure \@ref(fig:MCDataCapture) is a
typical readout from the MCMIX-OD Multicultivator software. Real time OD
measurements eliminate intrusive subsampling of sterile cultures and
provide high resolution chlorophyll and cell scatter proxies over the
duration of the experiment. All data from the Multicultivator were saved
as a comma separated values file and processed in R-Studio for
calculations of growth rate estimates and graphical plotting.

\newpage

<div class="figure">
<img src="../Output/Figures/MCMIX004_Picture.jpg" alt="**PSI MCMIX-OD Multicultivator.** The image illustrates the capability to set different spectral wavebands and light levels for individual culture tubes. Tubes 4 and 7 have oxygen optodes inserted for real-time dissolved oxygen concentration measurements. Real time Optical Density (OD) measurements eliminate intrusive subsampling of sterile cultures." width="2909" />
<p class="caption">(\#fig:MCpicture)**PSI MCMIX-OD Multicultivator.** The image illustrates the capability to set different spectral wavebands and light levels for individual culture tubes. Tubes 4 and 7 have oxygen optodes inserted for real-time dissolved oxygen concentration measurements. Real time Optical Density (OD) measurements eliminate intrusive subsampling of sterile cultures.</p>
</div>

\newpage

## Data management and analysis {.unnumbered}

%%%%%% Taken from my thesis word for word, need to reword and shorten %%%%

Data from the Multicultivators were imported into R-Studio for data
management, growth rate calculations, statistics, and generation of
figures with the `ggplot2` package [@R-tidyverse]. The chlorophyll proxy
optical density (OD680 - OD720) or ΔOD was used to determine the growth
rate for each condition. We used a rolling mean from the RStudio `zoo`
package [@R-zoo] to calculate the average ΔOD data over a 1-hour window.
This was done to prevent extraneous data points from affecting the
growth rate estimates. A Levenberg-Marquardt algorithm
[@bellaviaLevenbergMarquardtMethod2018] modification of the non-linear
least squares fit equation using the R package `minpack.lm`
[@R-minpack.lm] was used to calculate growth rate (µ) using the logistic
equation \@ref(eq:GrowthRate):

```{=tex}
\begin{equation}
  µ = \frac{ΔOD_{max} × ΔOD_{min} × exp^{(µ × t)}}{ΔOD_{max} + (ΔOD_{min} × exp^{((µ × t) - 1)})}
  (\#eq:GrowthRate)
\end{equation}
```
where ΔOD~max~ is maximum ΔOD, ΔOD~min~ is minimum ΔOD, t is time
duration over the growth trajectory. Figure
\@ref(fig:deltaODLogGrowthPlot) is an example of a chlorophyll proxy
growth estimates fitted from the high resolution ΔOD measurements for
each tube in a Multicultivator. The residuals of the logistic growth
curve fit are shown and the growth spectral waveband is plotted and
illustrates the imposed PAR (µmol photons m^-2^ s^-1^) and photoperiod
(h). Although the chlorophyll proxy (ΔOD) growth rate was used in this
study, we also determined the cell scatter proxy (OD720) growth rate.
The correlation between the chlorophyll proxy growth rate and the cell
scatter proxy growth rate of *P. marinus* under all conditions examined
in this study was shown in Figure \@ref(fig:AllBalanceGrowthPlot) and
generally showed balance growth. The high cell scatter growth rate of
cultures that exhibited no chlorophyll proxy growth may be the logistic
model over-estimating the fits as the amplitude of the OD720 signal
maybe very small.

## Generalized additive model {.unnumbered}

%%%%%% Taken from my thesis word for word, need to reword and shorten %%%%

A Generalized Additive Model (GAM) was applied to examine the
relationship between the chlorophyll proxy (ΔOD) growth rate across the
blue spectral waveband, photoperiod and PAR levels for each *P.marinus*
ecotype in this study. The gam function from the R package `mgcv`
[@R-mgcv] was used to model the growth rate with smoothing terms to
indicate the 90, 50 and 10% quantiles. Only data below a standard error
tolerance of 30% of the fit was used in the model. Because of time
limitations, we were unable to conduct sufficient growth response
experiments for all the other spectral wavebands, except for the blue,
to fulfill the input requirements for the GAM. Therefore, our priority
was on studying the effect of blue light on growth trends, considering
that blue light is the most ecologically relevant spectral waveband for
deep ocean niches.

\newpage

# Results {.unnumbered}


<div class="figure">
<img src="../Output/Figures/MED4ProteinAttonated.png" alt="**fmole target protein per ug total protein for *Prochlorococcus marinus* MED4 (High Light (HLI) near surface clade).  ** Growth Photosynthetically Active Radiation (PAR) (µmol photons m^-2^ s^-1^) and spectral wavelength are in rows;  2 levels of imposed growth dissolved O~2~ concentrations (µM) are in columns. Numbers over each bar are fmole/ug" width="2952" />
<p class="caption">(\#fig:MED4ProteinAttonated)**fmole target protein per ug total protein for *Prochlorococcus marinus* MED4 (High Light (HLI) near surface clade).  ** Growth Photosynthetically Active Radiation (PAR) (µmol photons m^-2^ s^-1^) and spectral wavelength are in rows;  2 levels of imposed growth dissolved O~2~ concentrations (µM) are in columns. Numbers over each bar are fmole/ug</p>
</div>

\newpage



<div class="figure">
<img src="../Output/Figures/MIT9313ProteinAttonated.png" alt="**fmole target protein per ug total protein for *Prochlorococcus marinus* MIT9313 (Low Light (LLIV) deep ocean clade).  ** Growth Photosynthetically Active Radiation (PAR) (µmol photons m^-2^ s^-1^) and spectral wavelength are in rows;  2 levels of imposed growth dissolved O~2~ concentrations (µM) are in columns. Numbers over each bar are fmole/ug" width="2952" />
<p class="caption">(\#fig:MIT9313ProteinAttonated)**fmole target protein per ug total protein for *Prochlorococcus marinus* MIT9313 (Low Light (LLIV) deep ocean clade).  ** Growth Photosynthetically Active Radiation (PAR) (µmol photons m^-2^ s^-1^) and spectral wavelength are in rows;  2 levels of imposed growth dissolved O~2~ concentrations (µM) are in columns. Numbers over each bar are fmole/ug</p>
</div>

\newpage


# Supplemental {.unnumbered}


<div class="figure">
<img src="../Output/Figures/MED4PAR.png" alt="**Chlorophyll proxy growth rate (d^-1^) for *Prochlorococcus marinus* MED4 (High Light (HLI) near surface clade) vs. photoperiod (h).  ** 3 levels of growth Photosynthetically Active Radiation (PAR) (µmol photons m^-2^ s^-1^) are in columns;  3 levels of imposed growth dissolved O~2~ concentrations (µM) are in rows. Colors represent the actinic spectral waveband (nm). Large circles show mean or single determinations of growth rate from logistic curve fits (ex. Figure \@ref(fig:deltaODLogGrowthPlot)); small circles show values for replicate determinations, if any: replicates often fall with larger circles" width="4133" />
<p class="caption">(\#fig:MED4PAR)**Chlorophyll proxy growth rate (d^-1^) for *Prochlorococcus marinus* MED4 (High Light (HLI) near surface clade) vs. photoperiod (h).  ** 3 levels of growth Photosynthetically Active Radiation (PAR) (µmol photons m^-2^ s^-1^) are in columns;  3 levels of imposed growth dissolved O~2~ concentrations (µM) are in rows. Colors represent the actinic spectral waveband (nm). Large circles show mean or single determinations of growth rate from logistic curve fits (ex. Figure \@ref(fig:deltaODLogGrowthPlot)); small circles show values for replicate determinations, if any: replicates often fall with larger circles</p>
</div>

\newpage


<div class="figure">
<img src="../Output/Figures/SS120PAR.png" alt="**Chlorophyll proxy growth rate (d^-1^) for *Prochlorococcus marinus* SS120 (Low Light (LLIII) deep ocean clade) vs. photoperiod (h). ** 3 levels of growth Photosynthetically Active Radiation (PAR) (µmol photons m^-2^ s^-1^) are in columns;  3 levels of imposed growth dissolved O~2~ concentrations (µM) are in rows. Colors represent the actinic spectral waveband (nm). Large circles show mean or single determinations of growth rate from logistic curve fits (ex. Figure \@ref(fig:deltaODLogGrowthPlot)); small circles show values for replicate determinations, if any: replicates often fall with larger circles" width="4133" />
<p class="caption">(\#fig:SS120PAR)**Chlorophyll proxy growth rate (d^-1^) for *Prochlorococcus marinus* SS120 (Low Light (LLIII) deep ocean clade) vs. photoperiod (h). ** 3 levels of growth Photosynthetically Active Radiation (PAR) (µmol photons m^-2^ s^-1^) are in columns;  3 levels of imposed growth dissolved O~2~ concentrations (µM) are in rows. Colors represent the actinic spectral waveband (nm). Large circles show mean or single determinations of growth rate from logistic curve fits (ex. Figure \@ref(fig:deltaODLogGrowthPlot)); small circles show values for replicate determinations, if any: replicates often fall with larger circles</p>
</div>

\newpage


<div class="figure">
<img src="../Output/Figures/MIT9313PAR.png" alt="**Chlorophyll proxy growth rate (d^-1^) for *Prochlorococcus marinus* MIT9313 (Low Light (LLIV) deep ocean clade) vs. photoperiod (h). ** 3 levels of growth Photosynthetically Active Radiation (PAR) (µmol photons m^-2^ s^-1^) are in columns;  3 levels of imposed growth dissolved O~2~ concentrations (µM) are in rows. Colors represent the actinic spectral waveband (nm). Large circles show mean or single determinations of growth rate from logistic curve fits (ex. Figure \@ref(fig:deltaODLogGrowthPlot)); small circles show values for replicate determinations, if any: replicates often fall with larger circles" width="4133" />
<p class="caption">(\#fig:MIT9313PAR)**Chlorophyll proxy growth rate (d^-1^) for *Prochlorococcus marinus* MIT9313 (Low Light (LLIV) deep ocean clade) vs. photoperiod (h). ** 3 levels of growth Photosynthetically Active Radiation (PAR) (µmol photons m^-2^ s^-1^) are in columns;  3 levels of imposed growth dissolved O~2~ concentrations (µM) are in rows. Colors represent the actinic spectral waveband (nm). Large circles show mean or single determinations of growth rate from logistic curve fits (ex. Figure \@ref(fig:deltaODLogGrowthPlot)); small circles show values for replicate determinations, if any: replicates often fall with larger circles</p>
</div>

\newpage

# References {.unnumbered}