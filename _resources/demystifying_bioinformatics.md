---
layout: page
title: Demystifying Bioinformatics
description: An introduction to bioinformatics and genomic sequencing data
resource_number: 2
---

# Demystifying Bioinformatics

## What is bioinformatics?

### Bioinformatics defined:

Bioinformatics is an interdisciplinary field that develops computational methods and tools for analyzing biological data

### Disciplines that make up bioinformatics:

 1. Biology, which is the "study of living organisms, divided into many specialized fields that cover their morphology, physiology, anatomy, behavior, origin, and distribution."
 2. Computer Science, which is the "study of the principles and use of computers."
 3. Mathematics, which is the "abstract science of number, quantity, and space."

### What do bioinformaticians do?

Bioinformaticians analyze biological data using computers. The more accurate (but complex) answer is that there are three main things a bioinformatician does:

 1. Analyze data
 2. Develop methods/software
 3. Model biological systems/processes

 Analyzing data and developing methods/software are the focus of bioinformaticians in public health.

## Sequencing

### Sequencing technologies

#### Sanger sequencing

The first generation of sequencing technology. Uses chain termination during DNA replication to determine the DNA sequence.

#### Next generation sequencing (NGS)

AKA "high-throughput" or "massively parallel" sequencing.

NGS is an umbrella term for modern DNA sequencing technologies. NGS sequencing technologies can rapidly sequence DNA in parallel, and they are faster and more cost effective than the first generation of sequencing technologies that preceded them.

#### Short-read sequencing

The second generation of sequencing technology.

Examples include:

 - Illumina
	 - Uses sequencing by synthesis (SBS), a DNA sequencing method in which DNA polymerases and dNTPs are used to replicate (synthesize) the strand to be sequenced. A fluorescently labeled reversible terminator is imaged as each dNTP is added, and then cleaved to allow incorporation of the next base.
	 - Illumina sequence data can be paired or single-end. Single-read sequencing involves sequencing DNA from only one end. Paired-end sequencing allows users to sequence both ends of a fragment
 - Pyrosequencing (454; now defunct)
	 - Also uses SBS, but relies on the detection of pyrophosphate release and the generation of light upon nucleotide incorporation.
- IonTorrent
	- Also uses SBS, but relies on the detection of hydrogen ions that are released during the polymerization of DNA.

#### Long-read sequencing

The third generation of sequencing technologies

Examples include:

 - PacBio (HiFi)
	 - DNA polymerase in HiFi sequencing works its way around the circularized sample molecule many times over
 - Oxford Nanopore
	 - Uses electrical currents to thread negatively charged DNA through a nanopore. Disruption of the electrical current is used to determine the DNA sequence.

#### Short- vs long-read sequencing

Specifications and advantages vs disadvantages of each technology

Short-read sequencing:
 - 300 bp max read length
 - Millions of reads per run
 - 99.99999% accuracy
 - Low cost per sample
 -  Advantages: Low cost, highly accurate
 - Disadvantages: Difficult to assemble short-read data from highly repetitive genomes, as well as plasmids

Long-read sequencing:
 - 2.3 Mb reads
 - Thousands of reads per run
 - 98-99.9% accuracy (Nanpore and PacBio, respectively)
 - High cost per sample
 -  Advantages: Long reads can be used to assemble and resolve entire genomes and plasmids
 - Disadvantages: More expensive than short-read sequencing and less accurate (although significant improvements in accuracy have been made)

The Illumina platform has been a workhorse in public health and it’s hard to beat 99.9999% accuracy. However, shorter reads (150 - 300 base pairs) make reconstruction of genome difficult and inaccurate. Longer reads (1,000 - 2 million base pairs or longer) help resolve genome structure, which can allow us to identify plasmids and gene orientation. This technology is still expensive and less accurate, but it has been useful in various applications, including mobile laboratories where sequencing can be done in the field.

#### Sanger sequencing vs NGS

NGS is higher resolution (thousands vs millions of base pairs)
NGS can sequence more base pairs per day  (millions vs billions of base pairs)
NGS is not limited to the laboratory, some sequencers are now portable

### Types of sequencing

#### Whole genome sequencing (WGS)

Sequencing the entirety of the DNA sequence of an organism's genome. WGS data is the most common type of sequencing data analyzed by public health bioinformaticians.

Sidebar: What’s the difference between NGS and whole genome sequencing (WGS)?

WGS is the process of sequencing all of an organism’s genetic material i.e. its chromosome and plasmids. Not all sequencing is WGS. For example, using a method commonly referred to as targeted amplicon sequencing (see below), we can use NGS to sequence only specific parts of the genome we’re interested in, such as virulence or antibiotic resistance genes.

**In summary:** NGS is a technology, WGS is a technique, and we can use NGS to perform WGS.

#### Targeted sequencing

Sequencing specific area of interest in the genome, such as a gene or coding region.

#### Whole exome sequencing

Sequencing only the protein coding genes (exons) of the genome.

#### Amplicon sequencing

Sequencing DNA fragments amplified by PCR (AKA amplicons).

#### Hybridization capture

Sequencing a region of interest captured using long, biotinylated oligonucleotide baits (probes).

## The omics

There are many different type of omics:

**Genomics:** The study of all genes in an organism i.e. its genome.

Genomics is most common omics in public health; Most bioinformatic analyses in public health are focused on the genome.

**Transcriptomics:** The study of all RNA transcripts in an organism i.e. its transciptome.

**Proteomics:** The study of all the proteins in an organism, and their interactions, structure and composition i.e. its proteome.

**Metabolomics:** The study of small molecules (metabolites) in an organism i.e. its metabolome.

**The meta-omics e.g. metagenomics and metatranscriptomics:** The omic studies described above applied to microbial communities, rather than single species.

Metagenomic analyses are becoming increasingly common in public health e.g., wastewater sequencing.

## Working with sequence data

After sequencing, there are several types of sequencing files to work with:

### Sequencing file types

#### BCL files
BCL or Binary Base Call format is the raw datafile for illumina sequencing that holds the basecalls and quality. These files are created and updated in realtime as the machine is sequencing and are used to generate the fastq files.

#### .fastq / .fastq.gz files

Fastq files are files that contain sequence data (reads, which are fragments of sequenced DNA base pairs that are generated during sequencing, the raw data from a sequencing machine) and quality information. The .gz extension just informs you the file is compressed, to be covered later. It is the format in which sequencing data is most often kept in. The file is structured with each read labeled with '@'. The following line has the sequence bases for that read. The 3rd line has a '+', and the 4th line has the sequence quality (Phred score) for each base encoded in a letter format.

Example of two reads:
```
@M03478:141:000000000-C5B4D:1:1101:25956:10945 1:N:0:1
TTCCGTATTCATGCAACCTATGATGAAAGTATTAGTCGGTTACTCAATGTATTTGAGCGC
+
ABBBBCFFFFFFGGGGGGGGGG5GHHHHHGGHHHHHHGGGGFHHHHHHHHHHHHHFGHGG

@M03478:141:000000000-C5B4D:1:1101:26997:10945 1:N:0:1
ATTAAGCCAGTCTGGGCTTTGGGCAATTACAGTACCAAAGCAATATGGTGGTGCCGAAGT
+
CCCCCFFFFFFFGGGGGGGGGGGHHGHHHHHHHHHHHHHHHHHHHHHHGHGEFHHEFGGF
```

The label has the following information:
**Sequence Identifier**
M03478:141:000000000-C5B4D:1:1101:25956:10945
* **M03478** - the unique instrument name
* **141** - the run id
* **000000000-C5B4D** - flowcell id
* **1** - flowcell lane
* **1101** - tile number on the flowcell
* **25956** - x-coordinate of the cluster within the tile
* **10945** - y-coordinate of the cluster within the tile

**Sequence Description**
1:N:0:1
* **1** - the member of a read pair '1' is forward '2' is reverse
* **N** - the read is filtered 'Y' or "N"
* **0** - If the read is not identified as a control, then the value is zero. If the read is identified as a control, the number is greater than zero, and the value specifies what type of control it is.
* **1** - sample number from the sample sheet

From this information we can determine that both of reads shown above are fwd reads from the same flowcell tile in the same y position but different x positions.

##### phred score
Here is a break down of how the quality score is encoded on the read:
A phred score of 10 translates to a 1 in 10 chance of an incorrect basecall or 90% accuracy:
* 10 	1 in 10 	90%
* 20 	1 in 100 	99%
* 30 	1 in 1000 	99.9%
* 40 	1 in 10,000 	99.99%
* 50 	1 in 100,000 	99.999%
* 60 	1 in 1,000,000 	99.9999%

These are encoded on in the fastq as shown below
```
SSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSS.....................................................
 ..........................XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX......................
 ...............................IIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIIII......................
 .................................JJJJJJJJJJJJJJJJJJJJJJJJJJJJJJJJJJJJJJJJ.....................
 LLLLLLLLLLLLLLLLLLLLLLLLLLLLLLLLLLLLLLLLLL....................................................
 !"#$%&'()*+,-./0123456789:;<=>?@ABCDEFGHIJKLMNOPQRSTUVWXYZ[\]^_`abcdefghijklmnopqrstuvwxyz{|}~
 |                         |    |        |                              |                     |
33                        59   64       73                            104                   126
 0........................26...31.......40
                          -5....0........9.............................40
                                0........9.............................40
                                   3.....9..............................41
 0.2......................26...31........41

S - Sanger        Phred+33,  raw reads typically (0, 40)
X - Solexa        Solexa+64, raw reads typically (-5, 40)
I - Illumina 1.3+ Phred+64,  raw reads typically (0, 40)
J - Illumina 1.5+ Phred+64,  raw reads typically (3, 41)
    with 0=unused, 1=unused, 2=Read Segment Quality Control Indicator (bold)
    (Note: See discussion above).
L - Illumina 1.8+ Phred+33,  raw reads typically (0, 41)
```
Using the Illumina 1.8+ encoding a seeing an H in the fastq corresponds to a Phred score of 40. While a 0 corresponds to a Phred score of 15.

#### .fasta files

The fasta file format is a method of storing sequence data that has been assembled (which we'll discuss in a later section). The format includes a '>' that contains the sequence label followed by the sequence on the next line(s). The file can contain multiple sequences "multi-fasta" with each sequence starting with a '>'.

example of a couple of lines from the NP and NS segments of an influenza virus:
```
>A/Hong_Kong/4801/2014_834574_NP
gttaataatcactcactgagtgacatcaaagtcatggcgtcccaaggcaccaaacggtcttatgaacagatggaaactga
tggagatcgccagaatgcaactgagattagggcatccgtcgggaagatgattgatggaattgggagattctacatccaaa
>A/Hong_Kong/4801/2014_834575_NS
gtgacaaagacataatggattccaacactgtgtcaagtttccaggtagattgctttctttggcatatccggaaacaagtt
gtagaccaaaaactgagtgatgccccattccttgatcggcttcgccgagatcagaggtccctaaggggaagaggcaatac
```

#### .sam / .bam files

The sam (Sequence Alignment Map) and bam (Binary Alignment Map) file format is a format that allows you to store the reads from a fastq mapped to a reference sequence. The sam and bam files are the same except the bam file is a binary format so it cannot be read by a human. The binary format is useful because it can be compressed to take up less disk space and can be read by programs more easily.

If you are interested in learning more about what is in this file format please visit this [wiki article](https://en.wikipedia.org/wiki/SAM_\(file_format%29) on the topic.

#### Other file formats

There are many other files like .vcf (variant call format) or the .gff (GenBank Flat File Format). These other types can have many uses, but the fastq/fasta/bam files are the ones most often encountered.

### Sequencing file compression

File compression is simple a method of storing a file that has been reduced in size. This can apply to any file type including sequence data, music, videos, or whatever you keep on your computer. There are many types of file compression each with it's own set of pro's and con's. When working with sequencing data here a couple that are commonly used:

* zip (.zip) - a very common universal method of compressing things in the Windows environment not used very often for sequence data. Can compress multiple files or folders.
* tar (.tar) - a method of wrapping multiple files and folders together in linux. Doesn't apply any compression.
* gzip (.gz) - a very common universal method of compressing things in the linux environment, used a lot for compressing fastq files. Can only compress a single file so it is often used in combination with tar (.tar.gz).
* bgzip (.gz) - very similar to gzip but has added features that are used specifically for sam file formats. Often adds a bit of confusion since gzip cannot interact with these files.

File compression is an important part of bioinformatics since the files are often very large. Here is some examples of the data sizes involved and how much of a difference compression can help.

**Compressed:**
* *E coli* both set of reads ~200MB
* *E coli* sequencing run (16 isolates) ~4GB

**Uncompressed:**
* *E coli* both set of reads ~900MB
* *E coli* sequencing run (16 isolates) ~20GB

### How data is transferred

Sequencing data can be moved a number of ways. The most common approach to transferring data is **SFTP**. Interacting with databases and cloud utilities often have their own methods for transferring files securely and without loss but these methods often use a version of FTP, FTPS, HTTP, HTTPS, SCP, or SFTP.

* **FTP** or File Transfer Protocol is pretty universal but is not secure and does not comply with HIPAA regulations.
* **HTTP** or HyperText Transfer Protocol often used for accessing websites, is widely used but is insecure.
* **FTPS** or File Transfer Protocol over Secure Sockets Layer, the same as FTP but adds a layer of security
* **HTTPS** or HyperText Transfer Protocol over Secure Sockets Layer, the same as HTTP but with a layer of security. Side note: always look for the HTTPS:// when using websites that ask for either a login or personal information.
* **SFTP** or Secure File Transfer Protocol is a method of transferring files through an SSH or Secure Shell connection. SSH creates a secure connection through an unsecure network (most often the internet). This connection allows two computers to communicate across a network with confidentiality and integrity of data.
* **SCP** or Secure Copy is very similar to SFTP but more primitive. It can only transfer files it cannot do other things like delete files which SFTP can do.

Of all these methods **SFTP** is the most commonly used in Bioinformatics as it provides the most secure environment that allows the safe transfer of data.

## Sequence data quality

The first phase of working with raw sequencing reads is ensuring high quality basecalls. Here the phrase garbage in / garbage out holds true. Fastq files have both the basecalls and the quality or likelihood of a correct basecall. Before using this information, most bioinformatic analysis pipelines will trim the reads where the quality of the basecall drops below a specific threshold (usually around a Phred score of 30).

### Phred quality score

A primary quality metric is the Phred quality score (Q score), which measures the accuracy of base calling. The Phred methodology determines the quality scores for each base by comparing the data generated within tables that were generated from sequence traces where the correct sequence was known, for a specific sequencing platform. For most analyses, a score of Q30 is typically used. This value means that there is less than a 1/1000 probability of an incorrect base
call at each nucleotide. A number of different programs can be used to examine the Q score. The average Q score for a sequencing run can be found within the Sequence Analysis Viewer in Illumina. When looking at a single sample, the per base sequence quality within [FastQC](https://www.bioinformatics.babraham.ac.uk/projects/fastqc/) will help to visualize the quality score for raw fastq files.

### The problem with low quality bases
Bioinformatics programs can trim low quality bases, because they mostly occur at the ends of sequences. But why are low quality bases a problem?
1. Low quality bases affect variant calling and may produce differences between sequences that are not real. This can result in long branches on phylogenetic trees or incorrect clustering of isolates that are epidemiologically linked.
2. Too few high quality bases also affects genome coverage, because these regions are cut out. This can result in missing important genes, such as those used for determining serotypes, virulence factors, and toxins. Additionally, typing schemes are based on variants. If the depth of coverage is too low because of too much base trimming, variant calling is not supported with a high enough confidence and is not reliable. This results in certain bases or regions of the genome being excluded from comparisons.

There are other quality control measures that can also be used including removing the sequencing adapters from the ends of the reads or removing potentially contaminating sequences.

## Genome assembly

Genome assembly is the aligning and merging of DNA sequence data to reconstruct the original sequence. It is an essential part of the bioinformatic analysis process.

### Reference guided assembly

Reference guided assembly maps reads to a reference genome by identifying reads with similar nucleotides to the reference. A reference genome is a consensus sequence of DNA for an organism.

This method of genome assembly works well for organisms with a well-characterized reference genome and organisms with highly conserved gene content.

### *De novo* assembly

*De novo* is latin for "from the beginning."  It follows that *De novo* assembly is the assembly of sequencing reads without prior knowledge of the correct sequence or order of those reads, and *de novo* assembly does not rely on a reference genome.

The *de novo* assembly process:
Reads &#8594; Contigs &#8594; Scaffolds &#8594; Chromosomes

Overlapping reads are assembled into contigs. A contig is a contiguous length of genomic sequence. An assembly with only one contig is considered “complete.” It is not unusual for *de novo* assemblies to have many contigs, especially if short reads are used for assembly. However, an excess of contigs or very short contigs are indicative of a poor quality *de novo* assembly.

Scaffolds are assembled from joined and oriented contigs.

Whole chromosomes are assembled from joined and oriented scaffolds.

There are different types of assembly algorithms that assemblers use to reconstruct genomes. Understanding these algorithms is not necessary for an introduction to genome assembly, but you can read more about them in this [wiki article](https://www.sciencedirect.com/science/article/pii/S0888754310000492).

*De novo* assembly works well for species without a reference genome, as well as species with diverse gene content. *De novo* assembly should be used if you are interested in investigating gene content that is not present in all members of a species.

### Which method of genome assembly should you choose?

Whether you should use *de novo* assembly or reference guided assembly depends on the questions you are trying to answer. *De novo* assembly is useful when you are assembling a new genome you have no reference genome for, or when you are interested in analyzing novel gene content your reference genome does not encode.

Reference guided assembly is useful when you have a well annotated reference genome and the genome you are assembling is not very different from your reference genome.

## Genomic relatedness

### Methods for determining relatedness

Methods for determining genomic relatedness fall into two major categories:
1. Standardized
2. Non-standardized

### Standardized  methods

AKA sequence typing methods, these methods include MLST (multilocus sequence typing), cgMLST (core-genome multilocus sequence typing) and wgMLST (whole-genome multilocus sequence typing), which are all built on the same principle of using a standard set of multiple genes/gene fragments (loci) to characterize isolates. Unique sequences for each locus are assigned allele numbers and isolates are identified based on their allelic profiles

#### MLST

Uses the sequences of ~7 house-keeping gene fragments and is the lowest resolution of the ST methods

Still used to differentiate isolates, but phylogenetic analysis of only MLST loci is less common than it once was due to advances in sequencing and bioinformatics that have allowed for higher resolution analyses

#### cgMLST

A fixed and agreed upon number of loci of a species that are present in all isolates of a given group, or a subset of that group

Few pathogens share all genes, so comparisons of the core-genome of a given group provides high-resolution data across a group of related (but not identical) isolates

Higher resolution than MLST, as core-genomes can contain thousands of loci

#### wgMLST

All the loci of a given isolate are compared to equivalent loci in other isolates

Includes cgMLST loci and adds a selection of accessory loci as well.

Most applicable to single-clone pathogens with closed genomes or to very closely related variants of more diverse organisms

Highest resolution ST method.

#### Advantages and disadvantages of standardized methods

Advantages:
 - Loci used in ST schemes are readily maintained and shared among laboratories using the same or similar online databases
 - Data can be analyzed by laboratorians without formal training in bioinformatics
 - Can be high resolution  (in the case of cg/wgMLST)

Disadvantages of standardized/ST methods:
 - Requires database curation and defined/agreed upon schemes i.e. not all organisms of interest have schemes available
 - Can be low resolution (in the case of MLST)

#### Examples of standardized methods

 - PubMLST (>100 organisms have schemes available)
 - Pulsenet and Bionumerics

### Non-standardized methods

- Core-genome analysis
- SNP analysis

#### SNP analysis

Identifies single nucleotide differences between isolates and a single reference genome

Very high resolution (based on SNPs)

Not all organisms of interest have complete reference genomes, and ideally reference genomes should be closely related to the genome of the isolates of interest to identify informative SNPs

#### Core-genome analysis

Similar to cgMLST, relies on the analysis of genes present in all isolates of a population (usually 95-99% of isolates)

This complement of genes is not standardized, it is unique to the population you are analyzing on a population by population basis

Most useful for organisms that lack ST schemes, as well as an appropriate reference genome by which to perform SNP analysis

#### Advantages and disadvantages of non-standardized methods

Advantages:
 - Do not require predefined schemes
 - High resolution

Disadvantages:
 - No universal method for typing isolates
 - Can require bioinformatics expertise to perform

#### Examples of non-standardized methods
 - Dryad
 - MycoSNP

## Phylogenetics

### What's in a name?
First we’ll start by defining the word ‘phylogenetic.’ The prefix ‘phylo’ refers to a group of organisms, and ‘genetic’ refers to genes and a common origin. It follows that ‘phylogenetic’ refers to examining
the common origin (i.e. the relatedness) of a group of organisms using their genetic data.

### Understanding phylogenetic trees

Phylogenetic trees are branching diagrams that allow us to visualize the results of phylogenetic analyses and determine the relatedness of organisms. When we look at a phylogenetic tree, there are a few common terms we can use to describe it:

The very edge of a phylogenetic tree is where we see the organism’s name (whether it’s the sample name or the name of a species) which is called the **leaf**. These leaves are connected to each other by **branches**. Two branches connect back to a **node**, which is a common ancestor of the leaf. The node is a hypothetical organism that may not exist in nature. As we go further back on the tree, we start to see more isolates are connected and descend from a common ancestor. Clusters of isolates from a recent ancestor make up a **clade**.

A common misconception in interpreting phylogenetic trees is that isolates are closely related because they are vertically close to one another on the tree. However, the vertical placement of isolates can be changed by rotating a clade at a particular node. This can take isolates that are vertically close to each other and place them distant from one another. When we read phylogenetic trees, we should look horizontally across the tree and identify nodes that are the common ancestor of a clade.

### Evolving phylogenetic trees

Have you ever looked at a phylogenetic tree at the start of an outbreak and seen two isolates that look like they might be related, but by the end of an outbreak they are on two different branches and now appear unrelated? Which tree is correct? The short answer is both trees are correct!

The addition of isolates that are related will cause new clades to appear and develop. This does not mean that the original isolates were not related or that the original tree clustered the isolates incorrectly, but that there are other isolates more closely related that were added to the analysis.

### Bootstrapping time - let’s add statistics to our phylogenetic trees

When looking at a phylogenetic tree, how can we be confident in a cluster that is present? Through the use of bootstrap statistics, we can calculate a statistical percentage of how well the placement of each branch on the tree is supported.

Bootstrapping is performed by random resampling of aligned sequence data. The percentage is then calculated to reflect the percentage of times the resampled alignment cluster the isolates together on the tree. A bootstrap value is calculated for every node on the tree.

### Classification by clades

Classifying pathogen diversity below the species level is often done by examining where isolates are found on a phylogenetic tree. More specifically, pathogens can be classified by the clades they belong to on a phylogenetic tree. As a reminder, a clade is a group of organisms composed of a common ancestor and its descendants.

Grouping isolates into clades and naming those clades in a standardized way allows us to identify links between outbreaks that are closely related but circulating in different locations.

### Naming clades

On a small tree, it’s easy for us to give two clades simple and arbitrary names, but what about a larger tree with thousands of isolates and hundreds of potential clades? A more dynamic and robust naming system is needed to classify the sequences. Some key features of a good naming system are:
1. Diversity: A good naming system accounts for the global diversity of a pathogen and can be used to differentiate between clades found at a significant frequency with broad geographic spread.
2. Flexibility: A good naming system can accommodate genetic diversity as it emerges and allows new clades to be added to the naming system if they rise to an appreciable frequency.
3. Utility: The labels in a good naming system can provide information about a clade.
4. Simplicity: The labels in a good naming system are easy to remember and allow for an increasingly large number of clades to be added to the naming system.

### Phylogenetic tree inference

There are a number of methods for inferring phylogenetic trees. Understanding those methods is not necessary for a basic understanding of bioinformatics, but you can read more about those methods in this [wiki article](https://en.wikipedia.org/wiki/Computational_phylogenetics#Types_of_phylogenetic_trees_and_networks).

## Genomic epidemiology

Genomic epidemiology is the use of pathogen genomic data to determine the distribution and spread of an infectious disease and the application of this information to control public health problems.

Pathogens gain informative mutations during infection. Strains with the same mutations are more closely related. Mutations allow us to group samples into clusters that belong to the same transmission chains.

## Computer infrastructure for bioinformatics in public health

Efficient and well-designed computer infrastructure is essential for conducting bioinformatics analyses effectively. This webinar will outline a few basic concepts, considerations to think about, and useful resources when developing computer infrastructure for bioinformatics in public health.

### Assessing needs and capabilities of your organization

It is important to conduct a thorough assessment of your organization's needs and capabilities before investing in bioinformatics infrastructure.

Here a few key questions and considerations:
- How much data will you be processing? What are the projected data volumes? For example, are you dealing with hundreds or thousands of samples?
- What types of analyses will you perform? Examples include variant calling, antimicrobial gene detection, phylogenetic analyses, or metagenomic profiling.
- What does your current set up look like? Assess the existing computer infrastructure at your institution/organization, including available hardware, software, and network capabilities.
- Who is part of your bioinformatics teams? Determine the number of users and their data access requirements.
- What bioinformatics experience does your team have? Will you be developing pipelines and/or using readily available softwares?
- What barriers or limitation will you encounter when developing bioinformatics data infrastructure. Identify potential barriers or challenges, such as limited IT support or budget constraints.

It is important to consider your organization's use cases for bioinformatics and available compute infrastructure. The answers to the above questions will help guide your bioinformatics data infrastructure development plan.

### General overview of computing infrastructure

#### Operating systems:

- Linux distributions (e.g., Ubuntu, CentOS) are commonly used due to their stability, compatibility with bioinformatics software, and extensive community support.
- Windows OS
- Mac OS

#### Hardware requirements:

- Processors: Aim for at least 32 cores to handle parallel processing efficiently.
- RAM: 128 GB is a suitable starting point, but larger datasets may require more memory.
- Storage: Consider a combination of fast local storage for temporary data and network-attached storage (NAS) or storage area network (SAN) for long-term data storage.

Check out "A Practical Guide to Building Computational Infrastructure for Synthetic Biology" for more detailed information.

### Example of bioinformatics practices

#### Routine tasks common in public health labs:

- Processing viral sequences: This task typically involves quality control, read mapping, and variant calling, and can take several hours to days depending on the dataset size and computational resources.
- Bacterial processing: Analyzing bacterial genomic data may include assembly, annotation, and comparative genomics, which can take from hours to weeks depending on the complexity of the analysis and the available computational power.
- Post run processing for samples: Analyze relatedness of samples and or prepare a phylogenetic analysis for a number of samples.

Depending on your routine tasks, your compute infrastructure  may vary in order to meet the needs your organizations processing requirements.

### Approaches to acquiring/accessing bioinformatics Infrastructure

#### Linux workstation:

- Pros: Offers flexibility, control, and customization opportunities for individual researchers or small teams. Can be cost-effective for small-scale analyses.
- Cons: Limited scalability, potential hardware maintenance, and potential challenges in resource sharing and collaboration.

#### High-performance computing (HPC) - On premise:

- Pros: Provides high computing power, dedicated infrastructure, and local data storage. Enables parallel processing and large-scale analyses.
- Cons: Associated costs for hardware, maintenance responsibilities, and limited scalability beyond the available infrastructure.

#### Cloud computing:

- Pros: Offers tailored computing resources based on demand, unlimited scalability, ease of reproducibility, and cost efficiency. Provides control over the compute environment without the need for purchasing and maintaining hardware.
- Cons: Ongoing costs, data transfer considerations, and potential privacy concerns.
- Specific platforms like Terra.bio, AWS, and GCP are examples of cloud-based bioinformatics tools and infrastructure.

## Publicly Available Sequence Data

Making sequence data publicly available is essential to the growth and success of public health and the scientific community at large. There are a number of databases in which sequence data can be submitted to in order to be made publicly available. For example:

[NCBI (National Center for Biotechnology Information)](https://www.ncbi.nlm.nih.gov/search/) – Part of the National Laboratory of Medicine and National Institute of health. The Entrez Global Query Cross Database search system is widely adopted by NCBI for array of nucleotide and protein sequences, protein structures, PubMed, taxonomy, whole genome etc.
[European Nucleotide Archive](https://www.ebi.ac.uk/ena/browser/home) – "The European Nucleotide Archive (ENA) provides a comprehensive record of the world’s nucleotide sequencing information, covering raw sequencing data, sequence assembly information and functional annotation."
[GISAID](https://gisaid.org/) – "The GISAID Data Science Initiative promotes the rapid sharing of data from priority pathogens including influenza, hCoV-19, respiratory syncytial virus (RSV), hMpxV as well as arboviruses including chikungunya, dengue and zika. This includes genetic sequence and related clinical and epidemiological data associated with human viruses, and geographical as well as species-specific data associated with avian and other animal viruses, to help researchers understand how viruses evolve and spread during epidemics and pandemics."

### Submitting data to NCBI
https://submit.ncbi.nlm.nih.gov/

### Submitting data to GISAID
https://gisaid.org/publish/