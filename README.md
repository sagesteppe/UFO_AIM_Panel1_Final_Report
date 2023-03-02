# Uncompahgre Field Office Terrestrial Assess, Inventory and Monitor Final Report

A framework for the assembly of many chapters of work into a BLM style report.

This repository contains the code to assemble all Chapters of the AIM project into a final document. It also contains a loose guide to the R scripts and data we used for ths project.

## Layout of the final report:

1) Cover page
2) Report Identifier Information
3) Table of Contents
4) Introduction; Written Sections
   Introduction; Analyses
5) Sample Design, Stratification, and Plots Weights
6) Ecological Side Descriptions Completion Assessment
7) Ecological Site Description and Ecological Site Groups Comparision - Vegetation 'Benchmarks'
8) An Assessment of Drought Conditions

9) An overview of the Analytical Sections
10) Bareground
11) Soil Stability
12) Noxious Species
13) Plant Functional Diversity - Cover
14) Plant Functional Diveristy - Species
15) Rare Species
16) Floristic Quality Index

17) Glossary
18) Acknowledgements


All analyses which occurred at a local scale were recorded using the version control language 'git'. These data are all available at a local path at the Bureau of Land Management Office. However, I do not have Git Large File Service Access, and several spatial products will not be available on here. Hopefully my notes and links, which are contained in the scripts, are enough to allow you to readily acquire them. 

It is worth noting, essentially, all computations were performed outside of the Windows environment. Whenever possible, only open-source software was utilized, so that any interested Citizen, or other, may emulate and build upon these analyses without a large barrier to entry associated with expensive software subscriptions. E.g. Microsoft and ESRI licenses. Unfortunately, it was required to use ESRI due to data sharing speeds in the internal BLM system. If you are a person external to the Bureau , I believe (but am not positive if this is correct, nor the mechanism to do so) you can request a copy of the AIM Geodatabase (~ TerraDat). You can much more readily import this into R using the 'sf' package, and reading and listing layers. I envy you.

However, with that said, computational power may be a limit for some. Two different hardware environments will be referred to colloquially throughout these scipts. One computer referred to as 'lightscape' and another (seldom noted) as 'parkland'. Nearly all computations were performed on 'parkland', (hopefully) unless otherwise noted. The specs of Parkland and Lightscape are listed at the end of this page, and you should ensure you have appropriate compute power; in nearly all cases you should.

## Project Directory Structure:
This project utilizes the idea of *relative paths*. There are essentially two very common ways to 'identify' a location on a computers memory. The first can be thought of as form the root of the computer. For example, if your neighbor saw you on the street and asked you for directions to your favorite deli, you may only be able to state the directions from your house - *not* the location we are currently at. If the same neighbor asked you for directions to the deli you just ate at, you may only be able to give them directions from *where* you currently are. 

The path from the 'base' of a computer all the way to a file is called an 'absolute path'. 
> '/home/UserName/Documents/FavoriteDeli  

The path from the current location on a computer to where a file is located is called a 'relative path'.

If we were already in 'Documents' part of town (and this is where the example turns sour), we could simply navigate to Deli we just ate as:  
> './DeliWeJustAteAt'  
that first '.', just means 'LOOK FOR FOLDER HERE!!!' and (in most? programming languages) this can be shortened to:    
> 'DeliWeJustAteAt'  

Now let us consider one more possibility, we return to our office in the 'Documents' part of town, and our co-worker, 'Dave' asks where we ate for lunch, and wants to go out himself. We can give dave directions from our office.

For illustrative purposes the absolute path to our office is:  
> '/home/UserName/Documents/TheOffice' 

And we can give Dave directions like:
> '../DeliWeJustAteAt'

where '..', means go up one level, or 'out of the current building'. What a relative path does is make it easy to share project structures across multiple computers. 

Our whole project structure is essentially 'flat' and looks like this:


```
.
├── AIM_Field_rasters
├── AIM_Frame1_data
├── drought_geospatial
├── Get_Gridmet
├── GraphModulesEsds
├── NAIP
├── plot_post_stratification
├── UFO_AIM_Compliance
├── UFO_AIM_Design_Stratification
├── UFO_AIM_Panel1_Final_Report
├── UFO_cartography
├── UFO_cover_estimates_ESD_ESG
├── UFO_drought
├── UFO_elements_of_style
├── UFO_ESD_completion
├── UFO_ESD_manual_classification
├── UFO_noxious_weeds
├── UFO_Plant_Diversity
├── UFO_Soil_Stability
├── UFO_Weights_for_stratification
├── UFO_Weighted_Analyses
├── UFO_bareground
```

A suitable thing to do would be to create your own directory (folder) called, 'UFO_AIM', and just store these in there! And using relative paths you can leap frog back and forth between projects to grab data!

### Individual sub-project Directory Structures

each of the above folders, *mostly* follow the same substructure, here is the example from the 'drought_geospatial' directory. 

```
.
├── citations
│   ├── citations
│   └── literature
├── data
│   ├── processed
│   │   ├── SPEI
│   │   └── SPEI_coarse
│   └── raw
│       └── SPEI_coarse
├── results
└── scripts
```

## Github Repositories:

[Get_Gridmet](https://github.com/sagesteppe/getGridmet)  automate downloading data products from the Gridmet website. Used for Drought analyses.

[plot_post_stratification](https://github.com/sagesteppe/UFO_vegetation_classification) a framework for the generation of useful major vegetation strata at the scale of a single BLM field office.  

[UFO_AIM_Compliance](https://github.com/sagesteppe/UFO_AIM_Compliance)  Interim reporting throughout the life of the sample design, and analysis of nearly all indicators without plot weights.  

[UFO_AIM_Panel1_Final_Report](https://github.com/sagesteppe/UFO_AIM_Panel1_Final_Report)  A framework for the assembly of many chapters of work into a BLM style report.

[UFO_cover_estimates_ESD_ESG](https://github.com/sagesteppe/UFO_cover_estimates_ESD_ESG)  Compare the reference benchmark conditions for Ecological Sites, with 'Ecological Site Group' derived mean values.

[UFO_drought](https://github.com/sagesteppe/UFO_drought)     Calculate the Standardized Precipitation Evapotranspiration Index (SPEI) at the scale of a BLM Office scale. 
[UFO_elements_of_style](https://github.com/sagesteppe/UFO-elements-of-style)   Design elements for a consistent 5 year AIM report. We define palettes, ggplot themes, and write some function to automate plot creation for us.
[UFO_ESD_completion](https://github.com/sagesteppe/UFO_ESD_completion)  How much of each Ecological Site Description has been written? Which portions are present?
[UFO_ESD_manual_classification](https://github.com/sagesteppe/UFO-ESD_manual_classification)   Tools to help in retroactively identifying which ESD an AIM plot was located in. Helpful in Major Land Resource Area's which did not have their ES complete, or mapped to SSURGO, at the start of the sample design.
[UFO_noxious_weeds](https://github.com/sagesteppe/UFO_noxious_weeds)  
[UFO_Plant_Diversity](https://github.com/sagesteppe/UFO_Plant_Diversity)    
[UFO_Soil_Stability](https://github.com/sagesteppe/UFO_Soil_Stability)    
[UFO_Weights_for_stratification](https://github.com/sagesteppe/UFO_weighted_analysis_Strat)  
[UFO_Weighted_Analyses](https://github.com/sagesteppe/UFO_weighted_analyses)   
[UFO_bareground](https://github.com/sagesteppe/UFO_bareground)  

## Hardware Specs:

Parkland:  
12th Gen Intel(R) Core(TM) i7-12700H  
20 cores  
RAM - 32gb

Lightscape:  
11th gen Intel(R) Core(TM) i7---  
16 cores  
RAM - 128gb  
