## Homework 4

**Kevin Moyung**  
**A12609930**  
**Due November 20th, 2018**  

### Lecture 11. Introduction to Analysis of Genome Interaction Data

#### Question 1 (20 pts)

**Image-based techniques such as immunofluorescent imaging were used to visualize the
global chromatin configuration. However, these techniques suffer from low resolution and
cannot provide information of what promoters or enhancers are open or closed at a specific
cell stage. Fortunately, DNase-seq, MNase-seq and ATAC-seq were developed to study
open regions of chromatin globally. Information on chromatin open regions provided by
DNase-seq, MNase-seq, and ATAC-seq is largely based on chromatin accessibility of
enzymes used in these 3 NGS techniques.**

**(a) What are enzymes used in DNase-seq, MNase-seq, ATAC-seq, respectively? (10 pts)**

**DNase-seq:** A specific endonuclease called DNase 1 is used to digest the extracted DNA into fragments.  
**MNase-seq:** Both endonuclease and exonuclease are used. In particular, Micrococcal nuclease (MNase) is used to cut the extracted DNA without digesting the nucleosome-associated regions, allowing to study the open regions of chromatin effectively.  
**ATAC-seq:** Tn5 transposase is used to transpose sequencing adapter oligos into the gDNA of permeabilized, unfixed cells. An endonuclease is used.  

**(b) What is the information on chromatin open region that DNase-seq, MNase-seq, and ATACseq
provide, respectively? (10 pts)**

**DNase-seq:** Provides information on the exposed regions of chromatin.  
**MNase-seq:** Maps the closed regions that are protected by the nucleosome.  
**ATAC-seq:** Provides information on the exposed regions of chromatin, location of nucleosomes, and TF footprints.  

#### Question 2 (30 pts)

**Although ChIP-seq, DNase-seq, and MNase-seq, and ATAC-seq give us information on
DNA interactions, they cannot provide information on higher order DNA interactions. New
NGS techniques such as 3C, 4C, 5C, and HiC were developed to study DNA interactions in
3D.**

**(a) What is the main difference in term of DNA interactions between 3C and Hi-C technique? (5
pts)**

3C studies DNA interactions on a "one to one" basis while Hi-C studies all possible interactions in an "all to all" basis, which means it covers all possible interactions simultaneously in a high-throughput manner.  

**(b) Although techniques to study DNA interactions differ, they do share some similar steps in
each technique. Please re-order the following steps into the correct order. (10 pts)**

C. Crosslink  
B. Restriction enzyme digestion   
A. Reverse crosslink and sequence  
D. Align and summarize the contact  
  
**(c) Describe the main data analysis workflow of Hi-C from raw reads to data visualization. (15
pts)**

From raw reads, the data is pre-processed and then aligned to a reference sequence either via full read or chimeric alignment. The reads are then binned into groups (to increase frequency) and contact matrices are built, followed by data normalization and detection of intra/inter-chromosomal interactions via tools for calling TADs, separating active/repressive compartments, and identifying chromatin loops. This resulting information is then visualized as intra/inter-chromosomal heatmaps, circular plots, multi-dataset plots, or signal transformations.

### Lecture 12. Analysis of Hi-C Data, GITAR

#### Question 3 (20 pts)

**GITAR is an open source tool for analysis and visualization of Hi-C data. It includes data
pre-processing, data normalization, data visualization, and topological analysis.**

**(a) How does in-situ Hi-C protocol improve the data resolution? (10 pts)**

TODO

**(b) The pair-end sequencing of Hi-C fragments causes chimeric read pair derived from two
interacting chromatins. However, it may produce low mapping rate to reference genome or lower
mapping quality. How does GITAR deal with this problem of chimeric alignment? (10 pts)**

TODO

#### Question 4 (30 pts)

**(a) What are technical bias in Hi-C data? (10 pts)**

TODO

**(b) What are biological bias in Hi-C data? (10 pts)**

TODO

**(c) What is topologically associated domains (TADs) in cell nucleus? (5 pts)**

TODO

**(d) In topological domain (TAD) analysis of GITAR, it uses directionality index (DI) combined
with hidden Markov model (HMM) to determine the TAD regions. At the end, how does it
identify TAD boundaries? (5 pts)**

TODO
