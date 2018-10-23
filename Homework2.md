# Homework 2
## BENG 183

**Kevin Moyung**   
**A12609930**

## Question 1 (5 points)

### a. What is the fundamental idea of personalized medicine? (5 pts)

There exists personal variations in genome sequence and environmental exposure. Understanding genomic and transcriptomic diversity on an individual level can better match therapies with patients.  

## Lecture 5. Introduction to Machine Learning

## Question 2 (15 points)

### a. Describe how in general clustering algorithms works. Explain the general idea starting from data points to a dendrogram. (5 pts)

The goal of clustering is to discover distinct groups of genes and samples. Starting with a collection of N samples each represented by a p-dimensional feature vector x_i, i = 1, ..., p, divide these N vectors into k clusters so that objects within each cluster are more "similar" than objects between clusters. K is usually unknown. In the end, the clustering algorithm typically represents these clusters as a dendrogram with branches between the closest samples and clusters in a hierarchical form, from most similar up to least similar.

### b. What are the differences between hierarchical and k-means clustering algorithm? (10 pts)

Hierarchical clustering aims to first calculate the similarity between all possible combinations of two data points (individual clusters). Two most similar clusters are grouped together to form a new, combined cluster, and the similarity is recalculated. These steps are repeated until all data points end up in one large, high-level cluster. On the other hand, k-means clustering starts with a pre-defined k number of clusters. It calculates the closest mean vector between the data points and includes them in the corresponding cluster, recalculating the mean vector each time until a desired clustering scheme is achieved with k clusters. One main difference between the two algorithms is that k does not need to be specified for the hierarchical clustering, whereas k-means requires a prescribed k value in order to begin.

## Lecture 6. ChIP-seq

## Question 3 (40 points)

### a. Describe how ChIP-seq works. (10 pts)

The goal of ChIP-seq is to identify where select proteins (transcription factors) are bound to the genome. In order to achieve this, the cells under study are first cross-linked using formaldehyde to form covalent bonds between the binding proteins and the DNA itself. Then, the DNA is extracted and sonicated, producing sheared, soluble chromatins. Protein-specific antibodies designed to bind to the proteins are then introduced. Using a process called immunoprecipitation, the fragments of DNA with the bound antibody are filtered and isolated. These fragments are then cross-link reversed and washed, obtaining the purified DNA. From here, the DNA fragments are sequenced, where they are ultimately mapped back to the genome. To visualize where the binding proteins are located, the mapping frequency of the reads are shown in a diagram, with the highest intensity being the region where the binding most likely occurred. 

### b. Two genes A and B are quantified by RNA-seq in two different experiments. For gene A, there are a total of 20,000,000 reads and 200 reads are within A. For gene B, there are a total of 10,000,000 reads and 10,000 reads are within B. The length of A and B are 7,000bp and 10,000bp respectively. Calculate the reads per kilobase million (RPKM) for gene A and B. (15pts) 

Gene A: 1.429 RPKM

Gene B: 100 RPKM

## Question 4 (15 points)

### You have a transcription factor (TF) with some binding motif. I.e: Suppose that given this motif you have an algorithm that can tell you whether or not your TF will bind some DNA of length 18. You also have a segment of DNA (oligo_x) that this algorithm tells you will be bound. Outline how you could determine whether or not this TF binding your oligo_x is statistically significant. (15 pts)

One way to determine whether or not the oligo_x binding site is statistically significant is to use a control run using a known transcription factor on a known DNA strand that does not bind. Similar to viewing the ChIP-seq peaks in a genome browser, for example, we can view the results side by side, identifying the locations with noisy peaks that are not significant. If oligo_x has a high intensity peak that is differentially shown compared to the control run, we can conclude that the oligo_x binding site is significant.

## Lecture 7. Genome Interaction Techniques I

## Question 5 (15 points)

### a. How does genome fold into nucleus? (from double-stranded DNA to chromosome) (5 pts)

Starting from a short region of the DNA double helix, it is first wrapped around histones, similar to a "beads on a string" forming chromatin. Then, these 30 nM chromatin fibers are tightly packed into nucleosomes, leaving some sections of the chromosome in an extended, open form. From there, sections of the chromosome and condensed, and the resulting chromosome is the mitotic chromosome.

### b. Describe the experimental procedures of Hi-C. (15 pts)

The goal of Hi-C is to select and identify regions where there is a high probability of adjacent DNA folding with each other. To begin, the cells are cross-linked with formaldehyde to form covalent bonds between adjacent DNA strands. Once "anchored", the DNA is digested with a restriction enzyme, leaving 5' overhangs. These 5' overhangs are then filled with nucleotides and biotin. Once, filled, the two strands are ligated together at that junction. After shearing the DNA and pulling down the biotin-marked fragments, the Hi-C library is created where these fragments are ultimately sequenced using paired-end sequencing. 

### c. Explain the role of contact matrix in Hi-C data analysis? (10 pts)

A contact matrix allows for a visualization of the frequency of ligation products between two loci on the same chromosome (intra-chromosome). The "intensity" of the heatmaps represents how frequently the two fragments within locus i and locus j interact with each other.

### d. Describe the two physical models on genome folding. (10 pts)

The two physical models on genome folding are equilibrium globule and fractal globule. The equilibrium globule model is a compact, densely knotted configuration of the genome where there is an abundance of overlaps. On the other hand, the fractal globule is a continuous fractal trajectory configuration that fills a 3D space without crossing itself. The fractal globule model is an attractice structure for chromatin segments because their "un-knotted" structure would facilitate unfolding and re-folding, which can represent gene activation and gene repression during the cell cycle.
