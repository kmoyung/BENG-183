## Homework 3

**Kevin Moyung**  
**A12609930**  
**Due 11/8/18**  

### Lecture 7 & 8. RNA-seq Analysis

#### Question 1 (15 pts)

**After a sequencing run, we obtain a raw FASTQ file. Then, we use TopHat for read alignment and Cufflinks for transcript compilation and gene identification.**

**(a) What is the content in a FASTQ file? (5 pts)**

A FASTQ file contains a file of sequenced reads along with additional information. For each read, there are four lines. The first line denotes the location of the read, specific sequencing machine used, as well as the read ID. The second line contains the actual sequence itself in standard one-letter code. The third line contains a "+" and may sometimes include a repeat of the first line. The fourth line contains an ASCII quality score for each base.

**(b) What is the meaning of Phred quality score = 30? (5 pts)**

Phred quality scores report the probability that the base call is incorrect. For Phred = 30, that means that there is a 99.9% base call accuracy, or a 1/1000 incorrect base call.

**(c) What is the meaning of CIGAR string? (5 pts)**

CIGAR string contains specific information about the mapping information at specific positions across the read. 

#### Question 2 (20 pts)

**The data matrix that we are discussing in class is transcripts per million (TPM) metric for gene expression.**

**(a) What two normalizations are applied to raw read count data to get the TPM metric?**

The first is RPK, which is done by dividing the read counts by the effective length of the genes in kilobases. Then, to achieve the "per million" scaling factor, all the RPK values are summed and the number is divided by 1,000,000. In the end, to obtain TPM, just divide the RPK value by the "per million" scaling factor.

**(b) Why are these normalizations important? (5 pts)**

These normalizations are important because they account for sequencing depth and gene length, which vary between samples/genes/sequencing technologies.

**(c) How does TPM differ from FPKM? (5 pts)**

TPM differs from FPKM in that the order of operations is essentially swapped around. For FPKM, in contrast to TPM, you would divide the read counts by the "per million" scaling factor and the gene length in kilobases, but TPM involves dividing the read counts by the gene lengths beforehand. TPM also differs in that the sum of all TPM values should equal to 1 million, which is more useful when comparing gene expression across samples.

#### Question 3 (10 pts)

**(a) What is count uncertainty and count dispersion? (5 pts)**

Count uncertainty is the fact that reads can be shared across multiple genes because of shared genetic data. Count dispersion is the fact that the number of reads produced is highly variable between replicates.

**(b) What contents are included in the output file of Cuffdiff? (5 pts)**

The output file of Cuffdiff is similar to a CSV format. It contains the following data fields: test id, gene id, gene, locus, sample 1, sample 2, value 1, value 2, log2(fold change), test stat, p value, q value, and whether or not it was significant.

### Lecture 10. Genome Interaction Techniques II

#### Question 4 (10 pts)

**(a) How much content in the human genome is protein-coding and non-protein coding genes? (5 pts)**

5% of the human genome is protein-coding, and the other 95% are non-protein coding.

**(b) What is the challenge of studying RNA-RNA interaction? (5 pts)**

There is an astronimcal number of possible RNA pairs, meaning the number of interactions are extremely large.

#### Question 5 (25 pts)

**(a) What is the main information that MARIO provided? (5 pts)**

MARIO provides a high-throughput mapping of RNA-RNA interaction networks using an in-vivo pipeline.

**(b) Describe how MARIO works. (10 pts)**

The key part of this technology is to convert each pair of interacting RNAs into a unique piece of DNA and using next-gen sequencing to produce a high-throughput output. First, a biotin-labeled RNA linker is ligated to an RNA molecule. If there's another neighboring molecular, it will be ligated to the RNA fragment, producing a chimeric RNA, RNA1-linker-RNA2. These chimeric RNAs are purified, reverse-transcribed, and then sequenced. These fragments represent interacting pairs of RNA. 

**(c) What is the novelty and advantages of MARIO? (10 pts)**

The novelty about this technology converts the interaction of RNA-RNA pairs into DNA. Two main advantages about MARIO are: 1) an unbiased selection marker using biotin-labeled RNA linkers. This allows for a high-throughput technology. 2) This method does not introduce synthetic nucleotides or recombinant DNA before the experiment, allowing this technology to be applicable directly to human tissues.

#### Question 6

**(a) What is the main information that MARGI provided? (5 pts)**



**(b) What are the two conclusions of non-coding RNA interaction studies by using MARGI techniques? (10 pts) Hint: Use the study that covered in class to answer this question.**
