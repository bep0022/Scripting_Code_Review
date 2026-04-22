# Scripting_Code_Review
Repository for the code review assignment in the Scripting for Biologists Course

### Background 

[Karimian et al. 2024](https://doi.org/10.1126/science.ado0431) develops a method for chromosome end-specific telomere sequencing and quantification that they coin "telomere profiling." While they developed this method in a human genome sequencing dataset for the intended use of clinical biomedical research, it is also widely applicable across other disciplines. Because vertebrates share the same telomeric repeat, TTAGGG, I expect the code produced in Karimian et al. will be relatively easily translatable for my own data.

I have selected this paper for my code review because I intend to implement their analysis for my own data (both in my dissertation and for the Scripting Class Project). Briefly, my overarching goal is to quantify the differences in telomere lengths on the homogametic sex chromosomes in males and females, and investigate the effect treatment (age in CH 1 and heat stress in CH 3) may have on telomere length. In a similar sequencing method, I have obtained selective seqeuncing Nanopore MinION data for the brown anole lizard and in the future will also be applying this method to the zebra finch genome. 

### Brief Summary

Karimian et al. 2024 produced two GitHub repositories containing their developed packages for telomere profiling.
With TeloBP/TeloNP, by inputting a reference genome (.fa, .fna, .fasta) you are able to output a file (.csv) containing the telomere-subtelomere boundary coordinates. Once the boundary indicating the beginning of the telomere sequence is determined, by inputting basecalled sequence files (.fastq) you are able to output a file (.csv) containing the telomere lengths on each chromosome/chromosome arm.
With TeloPeakCounter, by inputting the extracted signal data (.tsv) including the read identification and the raw current values from the Nanopore sequencing output you are able to output a file (.txt) with the counts of the repetitive telomeric peaks in the signal data.

Github Repository Links:

-   [TeloBP/TeloNP](https://github.com/GreiderLab/TeloBP)
-   [TeloPeakCounter](https://github.com/GreiderLab/TeloPeakCounter/tree/master)

As requested, my review below focuses on the code associated with Karimian et al. 2024 rather than the manuscript itself.

### Major Comments

TeloBP/TeloNP:
The python code is modularized and includes descriptive docstrings about the parameters. However, there is a lack of inclusion  of docstrings, sanity checks, and print statements written for aid in troubleshooting.

TeloPeakCounter:
The implementation of TeloPeakCounter is missing details. There is no clear suggestion to git clone the repository. The first statement in the usage section is "TeloPeakCounter reads in fast5 data, which can be extracted using SquigglePull." That is all that is said referring to SquigglePull, meaning the authors neglect to clarify that this is not one of their own functions. There is no citation or Github provided for the creators of SquigglePull. Additionally this statement refers to input being the raw Nanopore sequencing output file as specifically .fast5 because that is what SquigglePull is solely compatible with; however, Nanopore introduced the .pod5 raw data file format that replaced .fast5 files prior to the publication of this paper and repository. The python code for TeloPeakCounter is modularized, but lacks docstrings. Altogether, the lack of explanation in this repository makes for usage and troubleshooting to be quite difficult. 

### Minor Comments

TeloBP/TeloNP:
-   There are a lot of packages and dependencies required. Setting up and providing a conda environment would make this more accessible to the user.
-   There is a demo file with the input code and output in a Jupyter Notebook file; however, in addition to this to make the repository more reproducible I think it would be beneficial to add the starting file of this demo to the repository so that the user may following along themself. 
-   The usage options are described in the README, however the order of the steps for usage is not clearly laid out.

TeloPeakCounter:
-   Again, there are a lot of packages and dependencies required. Setting up and providing a conda environment would make this more accessible to the user.
-   This repository also includes a demo available as a Jupyter Notebook, but the README includes no mention of the demo. Detail the demo in the README.

### Citation

-   Karimian K., A. Groot, V. Huso, R. Kahidi, K.-T. Tan, S. Sholes, R. Keener, et al. 2024. Human telomere length is chromosome end–specific and conserved across individuals. Science 384:533–539.

