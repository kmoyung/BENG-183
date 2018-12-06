# Hi-C Technology and Analysis Tools 

*By Kevin Moyung, A12609930*

1. [Introduction](#1)
2. [Experimental Protocol](#2)<br>
    2.1. [In Situ Hi-C](#21)<br>
    2.2. [Single Cell Hi-C](#22)<br>
3. [Tools](#3)  
4. [Analysis](#4)<br>
    4.1. [Topologically Associated Domains](#41)<br>
  


## 1 Introduction<a name="1"></a>

With all of the 3C (Chromosome Conformation Capture) technologies, the underlying goal of Hi-C is to understand the physical structure of the genome by identifying the interactions between chromosomes [1]. Hi-C exists as a novel method with several key features compared to the previous technologies:

**Genome-Wide** - Hi-C can probe the interaction profiles of all loci versus all other loci across the entire genome, and this feature is called "all vs. all".  

**High Throughput** - The Hi-C technology is high throughput, meaning that it can generate billions of reads per run with the help of next-generation sequencing.  

This is a powerful method that provides pairwise information on the interactive genomic regions.

> In the next section, we will explore the experimental protocol as well as some Hi-C derived techniques.

## 2 Experimental Protocol<a name="2"></a>

The general Hi-C technique is as follows [2]:

1. **Crosslinking** - Cells are cross-linked and fixed using formaldehyde so that spatially adjacent DNA are covalently bonded.
2. **Digestion** - Restriction enzymes are used to digest the DNA, leaving 5' overhangs.
3. **Biotinylation** - Fragment overhangs are filled and marked with biotin.
4. **Ligation** - The biotinylated ends are ligated together.
5. **Size Selection** - The ligated fragments are filtered, sheared, and purified via sonication to a desired sequence length for sequencing.  

To better illustrate the experimental workflow, below is a diagram:

![](https://github.com/kmoyung/BENG-183/blob/master/hicoriginal.PNG)  

*A typical Hi-C workflow.*

### In Situ Hi-C<a name="21"></a>

![](https://github.com/kmoyung/BENG-183/blob/master/hicinsitu.PNG)

*In situ Hi-C.*

Developed by Rao et. al, in situ Hi-C is a derived technology that is performed inside the **nucleus** in order to **increase data resolution**. Instead of using the typical 6-base cutter (HindIII) restriction enzyme, the protocol uses a 4-base cutter (MboI) to generate more fragments. This is because HindIII has 1.72 million restriction sites in the human genome, compared to the 5.02 million restriction sites from MboI. 

### Single Cell Hi-C<a name="22"></a>

![](https://github.com/kmoyung/BENG-183/blob/master/hicsinglecell.PNG)

*Single cell Hi-C protocol.*

Single cell Hi-C, developed by Nagano et. al, is a powerful derivation of the original Hi-C method because it can create "snapshots" of thousands of chromatin interactions that occur simultaneously in a single cell. This leverages performing Hi-C within the cell nucleus.

> Next, we will take a look at the various tools that can help researchers explore Hi-C data.

## 3 Tools<a name="3"></a>

Hi-C and other genomic technologies within the 3C family have prompted the development of a suite of software tools to aid in the analysis and visualization of its high-throughput data. Because the amount of Hi-C data generated is large, several platforms have been developed to facilitate handling such data [3].

#### Juicer

Juicer is a multi-faceted tool that aligns, filters, normalizes, identifies, and compares topologically associated domains (TADs). In addition to such features, it can identify loops and compartments and be visualized all through its own "Juicebox" feature [4].

Features:
- Wide suite of Java command line tools for analysis
- Intuitive Java based web user-interface for visualization

![](https://github.com/kmoyung/BENG-183/blob/master/juicer.jpg)

#### Cooler

Cooler is a visualization tool that primarily builds and queries contact matrices at various resolutions. In addition to its normalization and visualization features, it stores Hi-C data in a sparse, compressed, binary file format called "cool" to improve analysis efficiency.

Features:
- Conforms to HDF5 binary data standard
- Less intuitive but more dynamic JavaScript-based visualizer

#### Hi-Five

Hi-Five is a Python package for efficient analysis of the entire Hi-C experiment, from mapped reads to interaction values. It is currently integrated into the open-source, web-based platform Galazy with an easy-to-use graphical interface [5].

#### HOMER

HOMER is a suite of tools for analyzing high-resolution Hi-C data, such as data generated from using 4-cutters in-situ. HOMER provides a comprehensive workflow, such as triming and read mapping, quality control, visualization, and differential calculations. It can identify chromatin compartments, TADs, and loops [6].

#### Fit-Hi-C

Developed by the Ay Lab at UCSD, Fit-Hi-C is a software package designed to assign statistical confidence estimates to interaction data from Hi-C. It works by applying a cubic spline function to the relationship between genomic distance and contact count. After the initial fit, outliers are removed and the process is repeated. It is a popular method to determine the statistical confidence of Hi-C data [7].

#### diffHic

diffHic is an alternative software that involves identifying significant changes in the interaction intensity, or differential interactions, between two or more biological conditions. While the conventional analyses focuses on the detection of statistically significant interactions of the genome, the creators of diffHic claim that this method is more statistically rigorous and thus may provide more biologically relevant results [8].

## 4 Analysis<a name="4"></a> 

A typical analysis pipeline involves the following steps:

1. **Raw reads processing**

2. **Alignment** 

Reads may be mapped with various tools and methods: full-read, chimeric, etc.

3. **Binning** 

Reads are grouped into fixed, non-overlapping genomic spans in order to increase the signal of the interaction. 

4. **Normalization**

Normalization aims to reduce biases during the experiment in order to obtain more accurate results. There are currently two types of normalization: **Explicit normalization,** which requires an understanding of the known bias sources and is corrected by integrating a probabilistic model to the data, and **Implicit normalization,** which is an iterative correction based on the assumption that all loci should have equal visibility.

5. **Interaction detection and visualization** 

Leveraging the intra-chromosomal/inter-chromosomal interactions, we can call TADs (see next subsection), separate active/repressive compartments, and identify chromatin loops that exist throughout the genome. 

> Specifically, we will focus on TADs for the remainder of this chapter.

### Topologically Associated Domains<a name="41"></a>

Chromatin is typically organized by active (A) and repressive (B) compartments, where **A** generally contains highly active genes and **B** generally contains inactive or repressed genes. In such compartments, there are areas where there is an extremely high frequency in interactions. These regions are called TADs, or topologically associated domains. 

TADs are typically bounded by CTCF and extruded by cohesins. As such, the prevailing hypothesis for TAD formation is that it is produced by loop extrusion. While the exact mechanism is currently being debated, the following figure shows the general mechanism of TAD formation:

![](https://github.com/kmoyung/BENG-183/blob/master/tad2.jpg)

Although the current hypothesis is being contended, single cell Hi-C studies have revealed new insights. It was found that there existed independent TAD signals in the *absence* of cohesin, a protein that has previously been found to be crucial in the mechanism. However, further work must be done in order to validate such findings. Using newer Hi-C methods, as we have learned from this chapter, we can hopefully gain a better insight in this field.

# Reference
[1]  Kyle P. Eagen.  Principles of chromosome architecture revealed by hi-c.Trends in Biochemical Sciences,43(6):469–478, Jun 2018.

[2]  Mattia Forcato, Chiara Nicoletti, Koustav Pal, Carmen Maria Livi, Francesco Ferrari, and Silvio Bicciato.Comparison of computational methods for hi-c data analysis.Nature Methods, 14(7):679–685, Jun 2017.

[3]  Bryan  R.  Lajoie,  Job  Dekker,  and  Noam  Kaplan.   The  hitchhiker’s  guide  to  hi-c  analysis:  Practicalguidelines.Methods, 72:65–75, Jan 2015.

[4]  Neva  C.  Durand,  Muhammad  S.  Shamim,  Ido  Machol,  Suhas  S.P.  Rao,  Miriam  H.  Huntley,  Eric  S.Lander, and Erez Lieberman Aiden. Juicer provides a one-click system for analyzing loop-resolution hi-cexperiments.Cell Systems, 3(1):95–98, Jul 2016.

[5]  Michael EG Sauria,  Jennifer E. Phillips-Cremins,  Victor G. Corces,  and James Taylor.  Hifive:  a toolsuite for easy and efficient hic and 5c data analysis.Genome Biology, 16(1), Oct 2015.

[6]  Sven Heinz,  Christopher Benner,  Nathanael Spann,  Eric Bertolino,  Yin C. Lin,  Peter Laslo,  Jason X.Cheng,  Cornelis  Murre,  Harinder  Singh,  and  Christopher  K.  Glass.   Simple  combinations  of  lineage-determining transcription factors prime cis-regulatory elements required for macrophage and b cell iden-tities.Molecular Cell, 38(4):576–589, May 2010.

[7]  F. Ay, T. L. Bailey, and W. S. Noble.  Statistical confidence estimation for hi-c data reveals regulatorychromatin contacts.Genome Research, 24(6):999–1011, Feb 2014.

[8]  Aaron T.L. Lun and Gordon K. Smyth.  diffhic:  a bioconductor package to detect differential genomicinteractions in hi-c data.BMC Bioinformatics, 16(1), Aug 2015.
