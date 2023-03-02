# Uncompahgre Field Office Terrestrial Assess, Inventory and Monitor Final Report
This repository contains the code to assemble all Chapters of the AIM project into a final document. It also contains a loose guide to the R scripts and data we used for ths project.

Layout of the final report:

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

Project Directory Structure:


Github Repositories:



===================
Hardware Specs:

Parkland:  
12th Gen Intel(R) Core(TM) i7-12700H  
20 cores  
RAM - 32gb

Lightscape:  
11th gen Intel(R) Core(TM) i7---  
16 cores  
RAM - 128gb  
