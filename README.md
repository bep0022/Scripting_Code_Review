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



### Minor Comments

-   

### Citation

-   Karimian K., A. Groot, V. Huso, R. Kahidi, K.-T. Tan, S. Sholes, R. Keener, et al. 2024. Human telomere length is chromosome end–specific and conserved across individuals. Science 384:533–539.

