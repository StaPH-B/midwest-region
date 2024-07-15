# Demystifying Bioinformatics

## What is bioinformatics?

### Bioinformatics defined:

"Bioinformatics is an interdisciplinary field that develops computational methods and tools for analyzing biological data"

### Disciplines that make up bioinformatics:

 1. Biology, which is the "study of living organisms, divided into many specialized fields that cover their morphology, physiology, anatomy, behavior, origin, and distribution."
 2. Computer Science, which is the "study of the principles and use of computers."
 3. Mathematics, which is the "abstract science of number, quantity, and space."

Figures to be included: 
 - Venn diagram of biology, computer science, and mathematics

### What do bioinformaticians do?

Bioinformaticians analyze biological data using computers. The more accurate (but complex) answer is that there are three main things a bioinformatician does:

 1. Analyze data
 2. Develop methods/software
 3. Model biological systems/processes
 
## Sequencing

### Sequencing Technologies

Sources:
- https://www.integra-biosciences.com/united-states/en/blog/article/dna-sequencing-methods-sanger-ngs

#### Sanger Sequencing

Sources: 
- https://www.sigmaaldrich.com/US/en/technical-documents/protocol/genomics/sequencing/sanger-sequencing
- https://letstalkscience.ca/educational-resources/backgrounders/sanger-sequencing

The first generation of sequencing technology. Uses chain termination during DNA replication to determine the DNA sequence. 

Figures to be included: 
 - Chain termination gel
 - Chromatogram

#### Next Generation Sequencing (NGS)

Sources: 
- https://www.integra-biosciences.com/united-states/en/blog/article/dna-sequencing-methods-sanger-ngs#Next_generation_sequencing

AKA "high-throughput" or "massively parallel" sequencing.

#### Short-read Sequencing
The second generation of sequencing technology.

Examples include:

 - Illumina
	 - Paired- vs single-end sequencing
 - Pyrosequencing (454; now defunct)

Figures to be included: 
 - Illumina sequencing process (includes bridge amplification)
 - Illumina flow cell color fluorescence
 - Pyrosequencing process
 
#### Long-read Sequencing

Sources:
 - https://www.pacb.com/blog/long-read-sequencing/

The third generation of sequencing technologies

Examples include:

 - PacBio (HiFi)
 - Oxford Nanopore

Figures to be included: 
 - HiFi/SMRT sequencing process
 - Nanopore sequencing process
 
#### Short- vs Long-Read Sequencing
 
Advantages and disadvantages of each technology

Short-read sequencing:
 - Advantages: Low cost, highly accurate
 - Disadvantages: Difficult to assemble short-read data from highly repetitive genomes, as well as plasmids
 
Long-read sequencing:
 - Advantages: Long reads can be used to assemble and resolve entire genomes and plasmids
 - Disadvantages: More expensive than short-read sequencing and less accurate (although significant improvements in accuracy have been made)

 
#### Sanger Sequencing vs NGS

### Types of Sequencing

Sources:
 - https://www.idtdna.com/pages/community/blog/post/let-s-talk-about-sequencing

#### Whole Genome Sequencing (WGS)

#### Targeted Sequencing

#### Whole Exome Sequencing (WES)

#### Amplicon Sequencing

#### Hybridization Capture

## The Omics

Genomics
Transcriptomics
Proteomics 
Metabolomics
The meta-omics

## Genome Assembly

### Reference Guided

### *De Novo*

## Genomic Relatedness

## Methods for Determining Relatedness

Methods for determining genomic relatedness fall into two major categories: 
1. Standardized
2. Non-standardized

### Standardized  Methods

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

Highest resolution ST method

#### Advantages and Disadvantages of standardized/ST methods

Advantages: 
 - Loci used in ST schemes are readily maintained and shared among laboratories using the same or similar online databases
 - Data can be analyzed by laboratorians without formal training in bioinformatics
 - Can be high resolution  (in the case of cg/wgMLST)

Disadvantages of standardized/ST methods:
 - Requires database curation and defined/agreed upon schemes i.e. not all organisms of interest have schemes available
 - Can be low resolution (in the case of MLST)
 
#### Examples of standardized/ST methods
 - PubMLST (>100 organisms have schemes available)
 - Pulsenet and Bionumerics

### Non-standardized methods

These methods include core-genome and SNP analyses

#### SNP analysis

Identifies single nucleotide differences between isolates and a single reference genome

Very high resolution (based on SNPs)

Not all organisms of interest have complete reference genomes, and ideally reference genomes should be closely related to the genome of the isolates of interest to identify informative SNPs

#### Core-genome analysis

Similar to cgMLST, relies on the analysis of genes present in all isolates of a population (usually 95-99% of isolates)

This complement of genes is not standardized, it is unique to the population you are analyzing on a population by population basis

High resolution

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
 - Utah’s core-genome pipeline
 - MycoSNP

## Infrastructure

## Public Repositories and Publicly Available Data

## Genomic Epidemiology

## Data Visualization

