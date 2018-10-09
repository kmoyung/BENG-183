## Homework 1

**Kevin Moyung**   
**A12609930**   
**Due 10/11/18**   

### Question 1 (15 points)

**a. Describe how polymerase chain reaction (PCR) works. (5 pts)**

PCR is an in vitro version of DNA replication that aims to amplify a specified fragment of DNA. For PCR to happen, it requires key enzymes. DNA polymerase helps elongate the new DNA strand by adding nucleotides, DNA ligase joins the lagging strand fragments, Primase creates a primer for replication, Helicase untwists the DNA into single strands, Topoisomerase relieves the stress of the twisting of DNA, and Single strand binding protein stabilizes the unpaired single strands of DNA. Along with these key enzymes, PCR is done using a thermocycler that alters the temperature, allowing for the amplification to occur: step 1 denatures the DNA by increasing the temperature to 95 C, step 2 anneals the primers to the single strands of DNA at 40 - 65 C, and step 3 elongates the DNA sequence by adding nucleotides at 72 C towards the 3' end. 

**b. Describe how microarrays work. (5 pts)**

Known cells are first extracted and separated into typically two different conditions (e.g Normal vs Cancer) and their RNA is obtained. Using a reverse transcriptase enzyme, the RNA is reverse transcribed into cDNA, where it is then fragmented into specific sequences and labeled different colors, depending on the condition (e.g normal or mutated). These labeled sequences are then placed into specific locations on the plate, forming the microarray. DNA samples in study are then placed on the glass, where specific sequences will hybridize with the cDNA. Finally, using lasers and other hardware, the fluorescent labels are detected to indicate which genes were active in the sample under study. 

**c. Why is the central dogma incorrect/incomplete nowadays (5 pts)**

The central dogma of molecular biology implies that by knowing the DNA, we can obtain the corresponding RNA, and thus the final protein that will be expressed. However, this is a largely incomplete conclusion due to what we know today about molecular biology. Although it is true that RNA is transcribed from DNA and proteins are expressed from the translation of RNA, regulational activity can significantly alter what genes are actually expressed and what proteins are produced in the human body. For example, alternative splicing can create various proteins depending on which exons are included in the final mature mRNA sequence, and DNA methylation/chromatin remodelling can dictate which regions of DNA are transcribed. Therefore, the central dogma has become a largely incomplete "blanket" statement for all living beings, especially for eukaryotes.

### Question 2 (15 points)

**a. Describe how Sanger sequencing works. (10 pts)**

Sanger sequencing was the first commercialized method of sequencing DNA. It utilizes PCR, or in-vitro DNA replication, to add modified nucleotides called ddNTPs in order to create truncated and fragmented DNA strands. These fragmented sequences, which come in various sizes depending on where the replication was terminated, are then run on a PAGE gel, which separates the mix of sequences by read length. Each base (A, T, C, G) is run separately in each lane of a gel. In the end, a scientist can read the gel to determine the actual sequence of As, Ts, Cs, or Gs in order by size of the sequence, from shortest to longest. Later, scientists were able to fluorescently label these nucleotides for a more automated sequencing innovation.

**b. What does the role of ddNTP play in Sanger sequencing? (5 pts)**

ddNTPs, or dideoxynucleotides, are engineered nucleotides that do not contain the 3'-hydroxyl that exist in typical dNTPs for DNA replication. The lack of this hydroxyl group prevents additional nucleotides to be added to the 3' end during elongation, effectively terminating that chain and ensuring that the ddNTP is the last nucleotide on the 3' end of that particular sequence. This forms the ingenuity behind the Sanger sequencing techinque, which takes advantage of these varied sequence lengths.

### Question 3 (10 points)

**a. Describe how Illumina's sequencing works. (10 pts)**

Illumina utilizes a technique called sequenceing by synthesis. First, DNA is fragmented into short sequences. The ends of these fragments are processed, and unique adapters are ligated to them. After, PCR is run to amplify these sequences. Then, using a flow cell that is coated with single strand oligonucleotides which correspond to the adapters, a bridge amplification is performed as the DNA fragments hybridize to the oligos, forming clusters on the flow cell. In the third step, the flow cell is loaded into a machine for automated cycles of elongation and imaging. Within each cycle, new nucleotides are added with fluorescent markers that, when visualized at particular locations, help identify the bases of the DNA fragments. 

### Question 4 (10 points)

**a. Draw the typical structure of coding genes. (5 pts)**

5' UTR -- Exon 1 -- Intron 1 -- Exon 2 -- Intron 2 -- Exon 3 -- Intron 3 -- Exon 4 -- 3' UTR

**b. Apart from coding genes, what are other annotated elements in the genome? (5 pts)**

Other annotated elements include: regulatory sequences such as promoters and enhancers, non-coding RNA such as miRNAs, tRNAs, rRNAs, lincRNAs, and repeat sequences along the genome.

### Question 5 (20 points)

**a. Describe five ways in which gene expression can be altered from Transcription to Post-Translation step. (5 pts)**

First, promoter activity highly affects whether or not transcription will occur for a particular coding region. When a promoter is activated, transcription occurs, but if promoters are inhibited, transcription does not occur. Second, DNA methylation/chromatin remodelling also affects transcription. Certain locations of the DNA may be modified to either upregulate or suppress transcription, while chromatin states (open or closed) can affect certain regions from being transcribed. Third, mRNA lifetime can affect translation. a particular transcript may not be translated if it becomes denatured. Fourth, alternative splicing can modify the resulting mature mRNA that is produced from pre-mRNA. The same pre-mRNA can be alternatively spliced to produce different proteins, depending on which exons are included. Finally, in post-translational modifcation, proteins may be inhibited due to chemical or other factors.

**b. What is alternative splicing? (5 pts)**

Right after transcription, a particular pre-mRNA can produce many different mature mRNAs depending on which of its exons are present. Particular exons of a gene region can be included or excluded, resulting in completely different proteins during gene expression. This allows more types of proteins to be expressed in the human genome from its 20,000 gene coding regions.

**c. If a gene has "x" number of exons, how many proteins could potentially be created? (5 pts)**

There can be (2^x) - 1 proteins made.

**d. If exactly "y" exons are to be retained in the final transcript, how many proteins can be created? (5 pts)**

There are y C x proteins possible. (C for combination)

### Question 6 (30 points)

**a. Describe how the experimental pipeline of RNA-seq works. (10 pts)**

First, samples of interest are obtained, typically pairwise in which there is a comparison between normal vs. a condition (e.g blood, tissue, cancer vs normal). Using RNA-seq protocols, the RNA are extracted from these samples, with most of the ribosomal filtered out via kits from Illumina, etc. Then, utilizing an enzyme, the RNA is reverse-transcribed into cDNA, fragmented into specified sequence lengths, and processed to include special adapters on each fragment. The fragments are sequenced (single-end or paired-end), and millions of reads are obtained, depending on the number and size of fragments. In the end, the reads are mapped to the genome, transcriptome, predicted exon junctions. Using this data, scientists can continue with downstream analyses.

**b. What are the steps of RNA-seq data analysis after RNA-seq run is performed? (5 pts)**

RNA-seq results are obtained from sequencing in a format called FASTQ, which contain raw reads of the fragments along with additional information like quality scores and sizes. These files are input for read alignment, which aligns the raw reads to a reference genome/transcriptome (in a FASTA format). After alignment, an additional file called a GTF, or gene annotation file, is input during transcript compilation to identify the genes. At this point, we have a data file that contains all of the genes along with their abundance levels for each of the samples. From this point on, a typical analyses performed is differential expression, which normalizes and computes the expression levels of genes between different samples and/or conditions. Visualization of these results is often a final step in this analysis.

**c. What goals can RNA-seq analysis achieve? (5 pts)**

RNA-seq analysis can achieve various goals, depending on the biological question at hand. Primarily, RNA-seq analysis allows for gene expression and differential expression, where genes are quantified in samples to observe which genes are upregulated or downregulated in various conditions. Second, RNA-seq analysis can allow for transcript discovery and annotation for alternative species. Third, mutations can be discovered, similar to variant calling, for particular genes. RNA-seq can also provide novel information about gene fusion that may have occurred in samples. Finally, using RNA-seq analysis, scientists can also perform RNA editing.

**d. What are four pros and four cons of RNA-seq compared to microarray? (10 pts)**

Pros
- RNA-seq can sequence novel transcribed regions
- RNA-seq does not require pre-defined procedures for specific transcripts
- Higher specificity and sensitivity
- Simple detection of rare and low-abundance transcripts

Cons
- RNA-seq can be expensive compared to microarray
- Storing RNA-seq data can be costly and challenging
- Analyzing RNA-seq data is challenging for general researchers
- RNA-seq is still relatively new compared to microarrays
