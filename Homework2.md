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

### b. Two genes A and B are quantified by RNA-seq in two different experiments. For gene A, there are a total of 20,000,000 reads and 200 reads are within A. For gene B, there are a total of 10,000,000 reads and 10,000 reads are within B. The length of A and B are 7,000bp and 10,000bp respectively. Calculate the reads per kilobase million (RPKM) for gene A and B. (15pts) 

## Question 4 (15 points)

### You have a transcription factor (TF) with some binding motif. I.e: Suppose that given this motif you have an algorithm that can tell you whether or not your TF will bind some DNA of length 18. You also have a segment of DNA (oligo_x) that this algorithm tells you will be bound. Outline how you could determine whether or not this TF binding your oligo_x is statistically significant. (15 pts)

## Lecture 7. Genome Interaction Techniques I

## Question 5 (15 points)

### a. How does genome fold into nucleus? (from double-stranded DNA to chromosome) (5 pts)

### b. Describe the experimental procedures of Hi-C. (15 pts)

### c. Explain the role of contact matrix in Hi-C data analysis? (10 pts)

### d. Describe the two physical models on genome folding. (10 pts)
