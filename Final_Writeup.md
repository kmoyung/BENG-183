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

With all of the 3C (Chromosome Conformation Capture) technologies, the underlying goal of Hi-C is to understand the physical structure of the genome by identifying the interactions between chromosomes. Hi-C exists as a novel method with several key features compared to the previous technologies:

**Genome-Wide** - Hi-C can probe the interaction profiles of all loci versus all other loci across the entire genome, and this feature is called "all vs. all".  

**High Throughput** - The Hi-C technology is high throughput, meaning that it can generate billions of reads per run with the help of next-generation sequencing.  

This is a powerful method that provides pairwise information on the interactive genomic regions.

> In the next section, we will explore the experimental protocol as well as some Hi-C derived techniques.

## 2 Experimental Protocol<a name="2"></a>

The general Hi-C technique is as follows:

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

Hi-C and other genomic technologies within the 3C family have prompted the development of a suite of software tools to aid in the analysis and visualization of its high-throughput data. Because the amount of Hi-C data generated is large, several platforms have been developed to facilitate handling such data.

#### Juicer

Juicer is a multi-faceted tool that aligns, filters, normalizes, identifies, and compares topologically associated domains (TADs). In addition to such features, it can identify loops and compartments and be visualized all through its own "Juicebox" feature (**cite juicer**).

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

Hi-Five is a Python package for efficient analysis of the entire Hi-C experiment, from mapped reads to interaction values. It is currently integrated into the open-source, web-based platform Galazy with an easy-to-use graphical interface.

#### HOMER

HOMER is a suite of tools for analyzing high-resolution Hi-C data, such as data generated from using 4-cutters in-situ. HOMER provides a comprehensive workflow, such as triming and read mapping, quality control, visualization, and differential calculations. It can identify chromatin compartments, TADs, and loops.

#### Fit-Hi-C

Developed by the Ay Lab at UCSD, Fit-Hi-C is a software package designed to assign statistical confidence estimates to interaction data from Hi-C. It works by applying a cubic spline function to the relationship between genomic distance and contact count. After the initial fit, outliers are removed and the process is repeated. It is a popular method to determine the statistical confidence of Hi-C data.

#### diffHic

diffHic is an alternative software that involves identifying significant changes in the interaction intensity, or differential interactions, between two or more biological conditions. While the conventional analyses focuses on the detection of statistically significant interactions of the genome, the creators of diffHic claim that this method is more statistically rigorous and thus may provide more biologically relevant results.

## 4 Analysis<a name="4"></a> 

A typical analysis pipeline involves the following steps:

1. **Raw reads processing**
2. **Alignment** - Full read or chimeric alignment
3. **Binning** 
4. **Normalization**
5. **Interaction detection and visualization** - Intra-chromosomal/Inter-chromosomal interactions

### Topologically Associated Domains<a name="41"></a>

## 5 Selected methods comparison<a name="235"></a> 
<table>
 <tbody>
    <tr>
        <th>Method</td>
        <th>Targets</td>
        <th>Resolution</td>
        <th>Notes</td>
    </tr>
    <tr>
        <td>3C <a href="http://refhub.elsevier.com/S2001-0370(17)30093-4/rf0535">[3]</a></td>
        <td>one-vs-one</td>
        <td>~1–10 kb<br></td>
        <td><ul><li>Sequence of bait locus must be known</li><li>Easy data analysis</li><li>Low throughput</li></ul></td>
    </tr>
    <tr>
    <td>4C <a href="http://refhub.elsevier.com/S2001-0370(17)30093-4/rf0545">[4]</a></td>
    <td>one-vs-all</td>
    <td>~2 kb</td>
    <td><ul><li>Sequence of bait locus must be known</li><li>Detects novel contacts</li><li>Long-range contacts</li></ul></td>
    </tr>
    <tr>
    <td>5C <a href="http://refhub.elsevier.com/S2001-0370(17)30093-4/rf0550">[5]</a></td>
    <td>many-vs-many</td>
    <td>~1 kb</td>
    <td><ul><li>High dynamic range</li><li>Complete contact map of a locus</li><li>3C with ligation-mediated amplification (LMA) of a ‘carbon copy’ library of oligos designed across restriction fragment junctions of interest
3C</li></ul></td>
    </tr>
    <tr>
    <td>Hi-C <a href="http://refhub.elsevier.com/S2001-0370(17)30093-4/rf0300">[6]</a></td>
    <td>all-vs-all</td>
    <td>0.1–1 Mb</td>
    <td><ul><li>Genome-wide nucleosome core positioning</li><li>Relative low resolution</li><li>High cost</li></ul></td>
    </tr>
    <tr>
    <td>ChIA-PET <a href="http://refhub.elsevier.com/S0168-9525(15)00063-3/sbref1405">[7]</a></td>
    <td>Interaction of whole genome mediated by protein</td>
    <td>Depends on read depth and the size of the genome region bound by the protein of interest</td>
    <td><ul><li>Lower noise with ChIP</li><li>Biased method since selected protein</li></ul></td>
    </tr>
 </tbody>
</table>

















# Referrence
[1] Schmitt, Anthony D., Ming Hu, and Bing Ren. "Genome-wide mapping and analysis of chromosome architecture." Nature reviews Molecular cell biology 17.12 (2016): 743.<br>

[2] Risca, Viviana I., and William J. Greenleaf. "Unraveling the 3D genome: genomics tools for multiscale exploration." Trends in Genetics 31.7 (2015): 357-372.<br>

[3] Dekker J, Rippe K, Dekker M, Kleckner N. Capturing chromosome conformation. Science 2002;295(5558):1306–11.<br>

[4] Simonis M, Klous P, Homminga I, Galjaard RJ, Rijkers EJ, Grosveld F, et al. High-res- olution identification of balanced and complex chromosomal rearrangements by 4C technology. Nature Methods 2009;6(11):837–42.<br>

[5] Dostie J, Richmond TA, Arnaout RA, Selzer RR, Lee WL, Honan TA, et al. Chromo- some Conformation Capture Carbon Copy (5C): a massively parallel solution for mapping interactions between genomic elements. Genome Res 2006;16(10): 1299–309.<br>

[6] Lieberman-Aiden E, van Berkum NL, Williams L, Imakaev M, Ragoczy T, Telling A, et al. Comprehensive mapping of long-range interactions reveals folding principles of the human genome. Science 2009;326(5950):289–93.<br>

[7] Fullwood, M.J. et al. (2009) An oestrogen-receptor-alpha-bound human chromatin interactome. Nature 462, 58–64.<br>

[8] https://github.com/hms-dbmi/hic-data-analysis-bootcamp/blob/master/HiC-Protocol.pptx.
