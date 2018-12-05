# Homework 5

**Kevin Moyung**
**A12609930**

## Lecture 14. RNA-RNA Interactions

### Question 1 (15 pts)

#### (a) How much content in human genome is protein-coding and non-protein-coding genes? (10 pts)

5% of the human genome is protein-coding, and the other 95% are non-protein coding.

#### (b) What is the challenge of studying RNA-RNA interaction? (5 pts)

There is an astronimcal number of possible RNA pairs, meaning the number of interactions are extremely large.

### Question 2 (35 pts)

#### (a) What is the main information that MARIO provided? (5 pts)

MARIO provides a high-throughput mapping of RNA-RNA interaction networks using an in-vivo pipeline.

#### (b) Describe the experimental process of MARIO. (15 pts)

The key part of this technology is to convert each pair of interacting RNAs into a unique piece of DNA and using next-gen sequencing to produce a high-throughput output. First, RNA pairs are crosslinked together, forming covalent bonds. Then, a biotin-labeled RNA linker is ligated to an RNA molecule. If there's another neighboring molecular, it will be ligated to the RNA fragment, producing a chimeric RNA, RNA1-linker-RNA2. These chimeric RNAs are purified, reverse-transcribed, and then sequenced. These fragments represent interacting pairs of RNA.

#### (c) What is the novelty and advantages of MARIO? (10 pts)

The novelty about this technology converts the interaction of RNA-RNA pairs into DNA. Two main advantages about MARIO are: 1) an unbiased selection marker using biotin-labeled RNA linkers. This allows for a high-throughput technology. 2) This method does not introduce synthetic nucleotides or recombinant DNA before the experiment, allowing this technology to be applicable directly to human tissues.

#### (d) In the bioinformatics pipeline of MARIO analysis, what is the main risk in the pipeline? (5 pts)

The main risk of the MARIO analysis pipeline is if it is unable to map the chimeric sequence to the genome.

## Lecture 15. RNA-DNA Interactions

### Question 3 (30 pts)

#### (a) What is the main information that MARGI provided? (5 pts)

MARGI provides information about RNA-genome interactions. As an example, it aims to find the locations of chromatin interacting with non-coding RNAs.

#### (b) Describe the experimental process of MARGI. (15 pts)

First, proximal DNA and RNA sequences are crosslinked. After, RNA is ligated, followed by DNA ligation. Using a protein to digest the nuclear material, the chimeras are pulled down and then reverse transcribed. After denaturation and library amplification, the fragments are finally sequenced using paired-end sequencing.

#### (c) What are two conclusions of non-coding RNA interaction studies by using MARGI techniques? (10 pts) Hint: Use the studies that were covered in class to answer this question.

Using MARGI techniques, researchers have found that the majority of transcription start sites are occupied by non-coding RNAs and that there exists a genome-wise anti-correlation between RNA attachment and H3K9me3. Another conclusion that was made is that RNA interaction sites are evolutionarily conserved.
