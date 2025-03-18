
# Demystifying Bioinformatics

## What is bioinformatics?

### Bioinformatics defined:

"Bioinformatics is an interdisciplinary field that develops computational methods and tools for analyzing biological data"

### Disciplines that make up bioinformatics:
Figures to be included: 
 - Venn diagram of biology, computer science, and mathematics.
 
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

Sources:
- https://www.integra-biosciences.com/united-states/en/blog/article/dna-sequencing-methods-sanger-ngs

#### Sanger sequencing

Sources: 
- https://www.sigmaaldrich.com/US/en/technical-documents/protocol/genomics/sequencing/sanger-sequencing
- https://letstalkscience.ca/educational-resources/backgrounders/sanger-sequencing

Figures to be included: 
 - Chain termination gel
 - Chromatogram

The first generation of sequencing technology. Uses chain termination during DNA replication to determine the DNA sequence. 

#### Next generation sequencing (NGS)

Sources: 
- https://www.integra-biosciences.com/united-states/en/blog/article/dna-sequencing-methods-sanger-ngs#Next_generation_sequencing

AKA "high-throughput" or "massively parallel" sequencing.  

NGS is an umbrella term for modern DNA sequencing technologies. NGS sequencing technologies can rapidly sequence DNA in parallel, and they are faster and more cost effective than the first generation of sequencing technologies that preceded them.

#### Short-read sequencing

Sources:
- https://www.illumina.com/science/technology/next-generation-sequencing/sequencing-technology.html
- https://www.illumina.com/science/technology/next-generation-sequencing/plan-experiments/paired-end-vs-single-read.html
- https://www.ebi.ac.uk/training/online/courses/functional-genomics-ii-common-technologies-and-data-analysis-methods/next-generation-sequencing/454-sequencing/
- https://www.thermofisher.com/us/en/home/life-science/sequencing/next-generation-sequencing/ion-torrent-next-generation-sequencing-technology.html

Figures to be included: 
 - Illumina sequencing process (includes bridge amplification)
 - Illumina flow cell color fluorescence
 - Pyrosequencing process
 - IonTorrent sequencing process

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

Sources:
 - https://www.pacb.com/blog/long-read-sequencing/
 - https://nanoporetech.com/platform/technology

Figures to be included: 
 - HiFi/SMRT sequencing process
 - Nanopore sequencing process
 
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

Sources:
 - https://www.idtdna.com/pages/community/blog/post/let-s-talk-about-sequencing
 - https://www.idtdna.com/pages/technology/next-generation-sequencing/dna-sequencing/targeted-sequencing
 - https://www.abmgood.com/assets/catalog/customservice/amplicon_sequencing/Amplicon-Seq-v4.png
 - https://geneticeducation.co.in/what-is-targeted-sequencing-and-how-does-it-work/
 - https://geneticeducation.co.in/wp-content/uploads/2023/05/targeted-sequencing-3.001-min.jpeg

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

Sources:
- https://be.mit.edu/research-areas/omics 
- https://www.britannica.com/science/omics

"The omics sciences share the overarching aim of identifying, describing, and quantifying the biomolecules and molecular processes that contribute to the form and function of cells and tissues."

There are many different type of omics:

**Genomics:** The study of all genes in an organism i.e. its genome.  

Genomics is most common omics in public health; Most bioinformatic analyses in public health are focused on the genome.

**Transcriptomics:** The study of all RNA transcripts in an organism i.e. its transciptome.  

**Proteomics:** The study of all the proteins in an organism, and their interactions, structure and composition i.e. its proteome.  

**Metabolomics:** The study of small molecules (metabolites) in an organism i.e. its metabolome.     

**The meta-omics e.g. metagenomics and metatranscriptomics:** The omic studies described above applied to microbial communities, rather than single species.

Metagenomics is the second most common omics in public health, and metagenomic analyses are becoming increasingly common in public health e.g. wastewater sequencing.

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

Sources:
 - https://www.researchgate.net/figure/6-Comparison-of-reference-assembly-and-de-novo-assembly-A-Reference-assembly-maps_fig4_321179957
 
Figures to be included: 
 - Figure of reference guided assembly (reference genome and reads)
-Oh the Places You'll Go as a  metaphor for reference guided assembly

Reference guided assembly maps reads to a reference genome by identifying reads with similar nucleotides to the reference. A reference genome is a consensus sequence of DNA for an organism.   

This method of genome assembly works well for organisms with a well-characterized reference genome and organisms with highly conserved gene content. 


### *De novo* assembly

Sources:
 - https://thesequencingcenter.com/knowledge-base/de-novo-assembly/

Figures to be included:
-Figure of *de novo* assembly (reads to contigs to scaffolds to chromsomes)
-Oh the Places You'll Go as a  metaphor for de novo assembly

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

Figures to be included:
 - Allele vs locus

Methods for determining genomic relatedness fall into two major categories: 
1. Standardized
2. Non-standardized

### Standardized  methods

AKA sequence typing methods, these methods include MLST (multilocus sequence typing), cgMLST (core-genome multilocus sequence typing) and wgMLST (whole-genome multilocus sequence typing), which are all built on the same principle of using a standard set of multiple genes/gene fragments (loci) to characterize isolates. Unique sequences for each locus are assigned allele numbers and isolates are identified based on their allelic profiles

#### MLST

Figures to be included:
 - MLST allele comparison
 
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

#### Advantages and disadvantages of standardized methods

Advantages: 
 - Loci used in ST schemes are readily maintained and shared among laboratories using the same or similar online databases
 - Data can be analyzed by laboratorians without formal training in bioinformatics
 - Can be high resolution  (in the case of cg/wgMLST)

Disadvantages of standardized/ST methods:
 - Requires database curation and defined/agreed upon schemes i.e. not all organisms of interest have schemes available
 - Can be low resolution (in the case of MLST)
 
#### Examples of standardized methods

Figures to be included:
 - Screenshot of PubMLST
 
 Examples:
 - PubMLST (>100 organisms have schemes available)
 - Pulsenet and Bionumerics

### Non-standardized methods

These methods include core-genome and SNP analyses.

#### SNP analysis

Figures to be included:
 - SNP example
 
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
 - MycoSNP

## Phylogenetics

### What's in a name?
First we’ll start by defining the word ‘phylogenetic.’ The prefix ‘phylo’ refers to a group of organisms, and ‘genetic’ refers to genes and a common origin. It follows that ‘phylogenetic’ refers to examining
the common origin (i.e. the relatedness) of a group of organisms using their genetic data. 

### Understanding phylogenetic trees

Figures to be included:
 - Dendrogram and circular phylogenetic tree
 - Phylogenetic trees that are identical, but have isolates rotated at TMRCA

Phylogenetic trees are branching diagrams that allow us to visualize the results of phylogenetic analyses and determine the relatedness of organisms. When we look at a phylogenetic tree, there are a few common terms we can use to describe it:

The very edge of a phylogenetic tree is where we see the organism’s name (whether it’s the sample name or the name of a species) which is called the **leaf**. These leaves are connected to each other by **branches**. Two branches connect back to a **node**, which is a common ancestor of the leaf. The node is a hypothetical organism that may not exist in nature. As we go further back on the tree, we start to see more isolates are connected and descend from a common ancestor. Clusters of isolates from a recent ancestor make up a **clade**.

A common misconception in interpreting phylogenetic trees is that isolates are closely related because they are vertically close to one another on the tree. However, the vertical placement of isolates can be changed by rotating a clade at a particular node. This can take isolates that are vertically close to each other and place them distant from one another. When we read phylogenetic trees, we should look horizontally across the tree and identify nodes that are the common ancestor of a clade.

### Evolving phylogenetic trees

Figures to be included:
 - Sequential outbreak phylogenetic trees

Have you ever looked at a phylogenetic tree at the start of an outbreak and seen two isolates that look like they might be related, but by the end of an outbreak they are on two different branches and now appear
unrelated? Which tree is correct? The short answer is both trees are correct!

The addition of isolates that are related will cause new clades to appear and develop. This does not mean that the original isolates were not related or that the original tree clustered the isolates incorrectly, but that there are other isolates more closely related that were added to the analysis.

### Bootstrapping time - let’s add statistics to our phylogenetic trees

Figures to be included:
 - Phylogenetic tree with bootstraps for every node on the tree

When looking at a phylogenetic tree, how can we be confident in a cluster that is present? Through the use of bootstrap statistics, we can calculate a statistical percentage of how well the placement of each branch on the tree is supported. 

Bootstrapping is performed by random resampling of aligned sequence data. The percentage is then calculated to reflect the percentage of times the resampled alignment cluster the isolates together on the tree. A bootstrap value is calculated for every node on the tree.

### Classification by clades

Figures to be included:
 - Phylogenetic tree with clades colored and labelled

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

Figures to include:
 - Color-coded mutations plotted on phylogenetic tree
 - Transmission tree

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

*Reference the article "A Practical Guide to Building Computational Infrastructure for Synthetic Biology" for more detailed information.*

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

### Data storage and transfer

- Discuss the importance of storage solutions in bioinformatics due to the large datasets commonly encountered in genomics and other biological disciplines.
- Highlight the need for redundancy, backup, and data archiving strategies to ensure data integrity and availability.
- On-premise vs in the cloud
- Address the challenges associated with transferring large volumes of data in bioinformatics.
- Discuss the significance of a robust network infrastructure to support data transfer, both internally within the institution/organization and externally with collaborators.
- Mention the importance of high-speed connections and consider options like dedicated network links or data transfer services for efficient data exchange.

## Publicly Available Sequence Data
Sources:
-https://hbctraining.github.io/Accessing_public_genomic_data/lessons/accessing_public_experimental_data_odyssey.html

Making sequence data publicly available is essential to the growth and success of public health and the scientific community at large. There are a number of databases in which sequence data can be submitted to in order to be made publicly available. For example:  

[NCBI (National Center for Biotechnology Information)](https://www.ncbi.nlm.nih.gov/search/) – Part of the National Laboratory of Medicine and National Institute of health. The Entrez Global Query Cross Database search system is widely adopted by NCBI for array of nucleotide and protein sequences, protein structures, PubMed, taxonomy, whole genome etc.
[European Nucleotide Archive](https://www.ebi.ac.uk/ena/browser/home) – "The European Nucleotide Archive (ENA) provides a comprehensive record of the world’s nucleotide sequencing information, covering raw sequencing data, sequence assembly information and functional annotation."
[GISAID](https://gisaid.org/) – "The GISAID Data Science Initiative promotes the rapid sharing of data from priority pathogens including influenza, hCoV-19, respiratory syncytial virus (RSV), hMpxV as well as arboviruses including chikungunya, dengue and zika. This includes genetic sequence and related clinical and epidemiological data associated with human viruses, and geographical as well as species-specific data associated with avian and other animal viruses, to help researchers understand how viruses evolve and spread during epidemics and pandemics."

### Submitting data to NCBI
https://submit.ncbi.nlm.nih.gov/

### Submitting data to GISAID
https://gisaid.org/publish/

## Data Visualization

### Data visualization with R

#### Intro to R
https://github.com/AbigailShockey/webinar_materials/tree/main/intro_to_R/

#### Intro to R Part I: Simple mathematics

R can be used to perform mathematical equations.
Addition is performed using + :

    2 + 2

Subtraction is performed using - :

    4 - 2

Multiplication can be performed using * :

    2 * 2

Exponents can be calculated using ** or ^:

    2**2
    2^2

R can also be used for mathematical comparisons.
Equal to:

    2 == 2

  
Greater-than/less-than:

    4 > 3

Greater-than or equal to/less-than or equal to:

    4 >= 2
    
    2 <= 4

Not equal to:

    3 != 2

When a comparison is true, R returns TRUE, and when a comparison is false,  R returns FALSE. 
This statement would return FALSE:

    2 > 3

And this statement would return TRUE:

    3 > 2

#### Intro to R Part II: Variables

Variables are symbolic names used to store information (just like in algebra!).  

Storing a value in a variable allows us to reference it later.

The <- symbol is used to assign variables in R:

    x <- 2
    x + 2

The result of this equation is 4  

The = sign can also be used to assign variables, but it is considered best practice to use <- :

    x = 2
    x + 2

The result of this equation is also 4  

Note: when you store a new value in a variable, the old value will be
overwritten.

There are rules for naming variables. Variable names can include letters, numbers, underscores and periods.  

The following are all valid variable names:

    myvariable <- 1
    
    my_variable <- 2
    
    my.varaible <- 3
    
    my_variable_2 <- 4

Variable names cannot include: spaces, dashes or symbols.  

Variable names cannot start with a number or underscore.  

Using these in variable names would cause an error.

In the examples above, all the variables were assigned numbers, but there are other types of data we can assign to variables.

Next we are going to review four data types you can store in a variable.

1. Character: Characters A-Z and punctuation characters such as ? contained 
between single or double quotes:

    x <- "I like dogs"

2. Numeric: Real numbers with or without decimals:

    x <- 2

3. Integer: Real numbers without decimals; the L character tells R to store the number as an integer:

    x <- 2L

4. Logical: TRUE/FALSE?:

    x <- TRUE

We can use the class() function to determine what type of data a variable contains:

    x <- "I like dogs"
    class(x)

Side Note: Functions are blocks of code that perform a specific task, 
which have been given a name.In this case the function is to determine what the data's class is, and it has been given the name class.  

Information on any given function can be found by placing a ? before the function:

    ?class()

Information can also be found using the Help tab. R has many other useful built-in functions, which we will discuss in later sections.  

The result of an equation can be stored in a variable:

    x <- 1
    y <- x + 1
    y

The result of this equation is also 2.

#### Intro to R Part III: Vectors

Vectors are a type of data structure. They contain a set of values in a specific order. These values can be any of the data types we discussed in Part II.  

This vector contains numerics:

    c(1,2,3)

While this vector contains characters:

    c("A", "B", "C")

Vectors can include a mix of data types. R will store the values in the vector below as strings:

    c("A", 1, 4L)

Vectors can also contain repeats of the same value:

    c("A", "A", "B", "C")

Note: c() is a function that combines values into a vector. The c *must* be lowercase.

The length of a vector corresponds to the number of values in it.
This vector has a length of 3:

    c(1,2,3)

We can use the length() function to get the length of a vector.
Using this function confirms this vector has a length = 3:

    length(c(1,2,3))

Like the data types we discussed in Part II, vectors can be assigned to variables:

    my.vector <- c(1, 2, 3)

We can also perform mathematical functions on vectors.
This equation will add 2 to every value in my.vector:

    2 + my.vector

While this equation will raise 2 to the nth power for very value in the vector:

    2**my.vector


Each value in a vector has an index that can be used to reference it.
Indices are represented by numbers.  

The 1st value in a vector is index 1, the 2nd is index 2, etc. Values in a vector can be retrieved using []:

    my.vector <- c("A", "B", "C")
    
    my.vector[1]
    
    my.vector[2]
    
    my.vector[3]

A colon (:) can be used to retrieve values between two indices:

    my.vector[1:2]

A vector of numbers can also be used to retrieve the values at those indices:

    my.vector[c(1,2)]

The values in a vector can be sorted using sort(). If given numerics, R will sort them in numerical order:

    unsorted.vector <- c(1, 3, 2, 4)
    sorted.vector <- sort(unsorted.vector)
    sorted.vector

If given letters, R will sort in alphabetical order based on the first letter
in each value in the vector:

    unsorted.vector <- c("cat", "B", "aardvark", "D")
    sorted.vector <- sort(unsorted.vector)
    sorted.vector

If given letters AND numbers, R will sort the numbers first, then the letters:

    unsorted.vector <- c("1", "400", "4", "100", "A", "C", "B")
    sorted.vector <- sort(unsorted.vector)
    sorted.vector

Note: Even though 4 is less than 100, 100 comes before 4 in this sorted vector, because the numbers in this vector are classified as characters.

Vectors can be sorted in reverse order by adding the 'decreasing'
argument. By default, vectors are sorted in increasing order:

    unsorted.vector <- c(1, 3, 2, 4)
    sorted.vector <- sort(unsorted.vector, decreasing = T)
    sorted.vector

Two vectors can be joined by making a vector of vectors:

    vector.A <- c("A","B","C")
    vector.B <- c("D","E","F")
    vector.X <- c(vector.A,vector.B)
    vector.X

Here are several useful functions for dealing with vectors:

    my.vector <- c(1,1,2,3,3,3,4,5)

min() gives us the smallest value of a vector:

    min(my.vector)

max() gives us the largest value of a vector:

    max(my.vector)

mean() gives us the mean of a vector:

    mean(my.vector)

median() gives us the median of a vector:

    median(my.vector)

#### Intro to R Part IV: Data frames

Data frames are a list of *equal-length* vectors that represent a table of data with rows and columns. Each column is a vector, and the number of rows is equal to the vector length. Equal length vectors can be assigned to a data frame using the data.frame() function:

    vectorA <- c(1,2,3)
    vectorB <- c(4,5,6)
    df <- data.frame(A=vectorA,B=vectorB)

By default, the rows of a data  frame are assigned a number from 1 to n. The $ symbol can be used to reference a specific column in the data frame:

    df$A

We can overwrite any column in the data frame.
In this case, we are storing values in the data frame, not a new variable:

    df$A <- c(7,8,9)
    df$A
    df$A <- df$A * 2
    df$A

Remember: The new column must be the same length as the original.  

R has several built-in data sets for use. We'll be using the Iris data set for the rest of the tutorial:

    df <- iris

We can use the functions nrow() and ncol() to get the number of rows and  columns in Iris, respectively:

    nrow(df)
    ncol(df)

We can use the head() function to print the first few lines of Iris:

    head(df) 

A data frame can be written to a file by using the write.table() function:

    write.table(x = df,
                file = "iris-data.tsv",
                row.names = FALSE,
                sep="\t")

Note: Always remember to use unique file names if you're working in the same directory, because R will overwrite any existing file of the same name.  

A data frame is written to your working directory by default. You can use getwd() to determine your current working directory:

    getwd()

A table can be read from a file and stored as a data frame using the 
read.table() function:

    new.df <- read.delim("iris-data.csv",
                         header = TRUE, sep = "\t")

A data frame is read from your working directory by default.  

Using the head() command we see that the df and new.df data frames are the same:

    head(new.df)

We can use the summary() function to summarize each column:

    summary(df)

#### Making figures with ggplot2
https://github.com/AbigailShockey/webinar_materials/tree/main/figures_with_ggplot2

https://youtube.com/playlist?list=PL-m0WlmGhvoDlJXhy6zGmCatvn5qXPXX9&si=q2TPG_n_fX7h98B-

#### Making figures with ggplot2 part I: ggplot2 basics
Making figures with ggplot2 part I: ggplot2 basics  

A. What is ggplot2?

https://ggplot2.tidyverse.org/  

"ggplot2 is a system for declaratively creating graphics, based on The Grammar of Graphics."  

The "grammar of graphics" is a system for describing the individual components that make up the figure or graphic we are visualizing.  

https://link.springer.com/book/10.1007/0-387-28695-0  

ggplot2 allows you to build a plot layer by layer.

In this section, we will go over the geom and aes layers. We will review layers that allow for further customization in later sections.  

For our example data, we will be using a table from the output of the
genome assembly QC program QUAST.  

First we will read in our table, store it as a variable, and view it:

    df <- read.delim("./data/quast_data.tsv", 
                     header = T, 
                     check.names = F,
                     stringsAsFactors = F,
                     sep = "\t")
    
    View(df)

ggplot() is the function for creating a new plot using ggplot2.  

As a reminder, we can use library() to load the package and ? to view its  documentation in the Help tab:

    library(ggplot2)
    ?ggplot2

Notice that using the ggplot() without a geom or aes results in a blank plot:

    ggplot(df)

B. Geometric objects aka geoms  

geoms specify what type of graph we are plotting e.g. line, bar, scatter, etc.  

You can use the help function to search for the different types of geoms available in ggplot2, or you can using the search bar in the help tab:

    help.search("geom_", package = "ggplot2")

C. Aesthetic mapping aka aes()

We use aes() to map variables to visual properties such as position (x, y),  color, shape, and size.  

Remember: aes() is a layer we add to our plot with our geom layer
We do this by placing aes() within the ggplot function.  

For example, plotting Largest Contig vs Total Length without a geom layer gives us an x- and y-axis, but no data on the graph:

    ggplot(df, aes(x=`Largest contig`, y=`Total length`))

We gave ggplot() the table and position of the data, but no geom.  

Adding geom_point() to our graph of Largest Contig vs Total Length will  plot a scatter plot of those data:

    ggplot(df, aes(x=`Largest contig`, y=`Total length`)) + 
      geom_point()

To plot those data as a line, we use geom_line():  

    ggplot(df, aes(x=`Largest contig`, y=`Total length`)) + 
      geom_line()

And if we wanted to include dots and lines, we use both geom functions:

    ggplot(df, aes(x=`Largest contig`, y=`Total length`)) + 
      geom_line() + 
      geom_point()

We can change the appearance, or aesthetic, of our plot by adding more parameters to aes().  

The properties we can change using aes() include things like:  
 - shape
 - size
 - color (outside color)
 - fill (inside color)
 - line type  

If we want to make a uniform change, we make that change outside of aes().  

For example, to change the color, size and shape of the points in our plot:

    ggplot(df, aes(x=`Largest contig`, y=`Total length`)) + 
      geom_point(size=3, shape=17, color="blue")

We can do the same for our line plot and change its color and linetype:

    ggplot(df, aes(x=`Largest contig`, y=`Total length`)) + 
      geom_point(size=3, shape=17, color="blue") +
      geom_line(size=2, linetype="dashed", color="purple")

Note: the numbers associated with point shapes and line types can be viewed with the following ggpubr commands:

    library(ggpubr)
    show_point_shapes()
    show_line_types()

If we want to map an aesthetic change to a variable, we make that change  inside of aes().  

For example, to change the shape and color of the points in our  scatter plot based on AMR profile:

    ggplot(df, aes(x=`Largest contig`, y=`Total length`)) + 
      geom_point(aes(shape=AMR))
    
    ggplot(df, aes(x=`Largest contig`, y=`Total length`)) + 
      geom_point(aes(color=AMR))
    
    ggplot(df, aes(x=`Largest contig`, y=`Total length`)) + 
      geom_point(aes(color=AMR, shape=Species))

We will discuss how to customize these figures further in a later section.

#### Making figures with ggplot2 part II: More geoms and different types of graphs

In this section we will go over more geoms and continue learning how to plot different types of graphs using ggplot2.

For our example data, we will be using the same assembly QC table from the previous section:

    df <- read.delim("./data/quast_data.tsv", 
                     header=T, 
                     check.names=F,
                     stringsAsFactors=F,
                     sep="\t")

A. Histograms

To plot a histogram, we use the geom geom_histogram(). We will start by plotting a histogram of N50:

    library(ggplot2)
    
    ggplot(df, aes(x=N50)) + 
      geom_histogram()

Notice that R prints the message:
"`stat_bin()` using `bins=30`. Pick better value with `binwidth`."

Additionally, our histogram is spread thin. We can change the amount of bins using the bin parameter:

    ggplot(df, aes(x=N50)) + 
      geom_histogram(bins=10)

We can change the color of our histogram using what we learned about aes() in the previous section:

    ggplot(df, aes(x=N50)) + 
      geom_histogram(bins=10, color="black", fill="lightgreen")

We can color our histogram by a specific variable using aes() and color or fill. 

For example, coloring our N50 histogram by Species:

    ggplot(df, aes(x=N50, fill=Species)) +   geom_histogram(bins=10)

We can change the position of the histogram's bars using the parameter position. Values for the parameter position are “identity”, “stack”, and “dodge”:

    ggplot(df, aes(x=N50, fill=Species)) +
      geom_histogram(bins=10, position="dodge")

ggplot also has the ability to add a line at the mean or median of our 
histogram with geom_vline():

    ggplot(df, aes(x=`Largest contig`)) +
      geom_histogram(bins=10) +
      geom_vline(aes(xintercept=median(`Largest contig`)), linetype="dashed", size=1)

B. Barplots

To plot a barplot, we use the geom geom_bar(). We will start by plotting the counts for each Species in the data set:

    ggplot(df, aes(x=Species)) + 
      geom_bar(stat="count")

Note: "count" is what we use to tell ggplot we want to graph counts of a particular variable.

coord_flip() can be used to plot the bars horizontally instead of vertically:

    ggplot(df, aes(x=Species)) + 
      geom_bar(stat="count") +    
      coord_flip()

color, fill, and aes() can be used to color and fill the bars:

    ggplot(df, aes(x=Species, color=Species, fill=Species)) +
      geom_bar(stat="count")
    
    ggplot(df, aes(x=Species, fill=Species)) +
      geom_bar(stat="count", color="black")

Multiple variables can be used in the barplot. For example, plotting the
the AMR counts and coloring the bars by species

    ggplot(df, aes(x=AMR, fill=Species, color=Species)) + 
      geom_bar(stat="count")

C. Box Plots

To plot a box plot, we use the geom geom_boxplot(). We will start by plotting a basic box plot of Species vs Total length:

    ggplot(df, aes(x=Species, y=`Total length`)) + 
      geom_boxplot()

Outliers in our data can sometimes make it difficult to see box plots as is, but we can remove them using the outliers parameter:

    ggplot(df, aes(x=Species, y=`Total length`)) + 
      geom_boxplot(outliers=F)

There are also options for changing the appearance of outliers.
Those options include outlier.color, outlier.shape, outlier.size, etc:

    ggplot(df, aes(x=Species, y=`Total length`)) + 
      geom_boxplot(outlier.color="blue", outlier.shape=15, outlier.size=3, alpha = .5)
    
    ?geom_boxplot

We can use coord_flip() to horizontally plot the the boxes:

    ggplot(df, aes(x=Species, y=`Total length`)) + 
      geom_boxplot(outliers=F) + 
      coord_flip() 

Like geom_vline(), geom_hline() can be used to plot a horizontal line:

    ggplot(df, aes(x=Species, y=`Total length`)) + 
      geom_boxplot(outliers=F) + 
      geom_hline(aes(yintercept=mean(`Total length`)), linetype="dashed")

Coloring our box plot by Species is the same as in previous examples:

    ggplot(df, aes(x=Species, y=`Total length`, fill=Species)) + 
      geom_boxplot(color="black")
    
    ggplot(df, aes(x=Species, y=`Total length`, color=Species)) + 
      geom_boxplot()

#### Making figures with ggplot2 part III: Axes and labels

In this section, we will review how to customize the axes and labels of your figures using ggplot2.  

For our example data, we will be using the same assembly QC table from the previous section:

    df <- read.delim("./data/quast_data.tsv", 
                     header = T, 
                     check.names = F,
                     stringsAsFactors = F,
                     sep = "\t")

A. Axes and titles

You may have noticed that ggplot2 labels the x and y axis using their
respective column names. Additionally, the plot has no title:

    library(ggplot2)
    
    ggplot(df, aes(x=Species, y=`Total length`)) + 
      geom_boxplot(outliers=F)

We can change those defaults using the xlab() and ylab() functions:

    ggplot(df, aes(x=Species, y=`Total length`)) + 
      geom_boxplot(outliers=F) +
      xlab("Assembly Species") +
      ylab("Assembly Length (bp)")

Alternatively, we can use the labs() function

    ggplot(df, aes(x=Species, y=`Total length`)) +    geom_boxplot(outliers=F) +   labs(x="Assembly Species",
           y="Assembly Length (bp)",
           title="Species Assembly Lengths")

ggplot2 also automatically chooses the limit, scale, and labels of an axis, but we can change those defaults as well.  

The xlim() and ylim() functions can be used to change the limit of an axis.  

1119861 is the highest x value and 12380070 is the highest y value of our line graph, so we'll choose values close to those as our x and y max. Our x and y min will be 0:

    ggplot(df, aes(x=`Largest contig`, y=`Total length`)) + 
      geom_line()
    
    ggplot(df, aes(x=`Largest contig`, y=`Total length`)) + 
      geom_line() + 
      xlim(0,1120000) +
      ylim(0,12400000)
    
    ggplot(df, aes(x=`Largest contig`, y=`Total length`)) + 
      geom_line() + 
      xlim(-1000000,1120000) +
      ylim(0,20000000)

To change the scale of an axis, we can use the scale_x and scale_y functions, which there are many to choose from

    help.search("scale_x", package = "ggplot2")

The functions for discrete variables include the word "discrete" and the  functions for  continuous variables include the word "continuous."  

The limits, breaks, labels, and names of each axis can be set with those parameters:

    ggplot(df, aes(x=`Largest contig`, y=`Total length`)) + 
      geom_line() +
      scale_x_continuous(limits=c(280000,1120000),
                         breaks=c(280000,560000,840000,1120000),
                         labels=c(280000,560000,840000,1120000),
                         name="Largest Contig (bp)") +
      scale_y_continuous(limits=c(3100000,12400000),
                         breaks=c(3100000,6200000,9300000,12400000),
                         labels=c(3100000,6200000,9300000,12400000),
                         name="Assembly Length (bp)") 

Instead of manually typing out the axis scale, we can use the seq.int() 
function to create it and store it in a variable:

    xmin <- 280000
    xmax <- 1120000
    x_scale <- seq.int(280000, 1120000, by = (xmax/4))
    
    ymin <- 3100000
    ymax <- 12400000
    y_scale <- seq.int(3100000, 12400000, by = (ymax/4)) 
    
    ggplot(df, aes(x=`Largest contig`, y=`Total length`)) + 
      geom_line() +
      scale_x_continuous(limits=c(xmin,xmax),
                         breaks=x_scale,
                         labels=x_scale,
                         name="Largest Contig (bp)") +
      scale_y_continuous(limits=c(ymin,ymax),
                         breaks=y_scale,
                         labels=y_scale,
                         name="Assembly Length (bp)") 

There are many other functions we can use to transform our continous axes.  

For example, we can reverse our axes:

    ggplot(df, aes(x=`Largest contig`, y=`Total length`)) + 
      geom_line() +
      scale_x_reverse() +
      scale_y_reverse() 

Or we can log transform them:

    ggplot(df, aes(x=`Largest contig`, y=`Total length`)) + 
      geom_line() +
      scale_x_log10() +
      scale_y_log10() 

We can also log transfom axes using the scale_x/y_continuous trans parameter:

    ggplot(df, aes(x=`Largest contig`, y=`Total length`)) + 
      geom_line() +
      scale_x_continuous(trans="log2") +
      scale_y_continuous(trans="log2")

As a reminder, you can view the other axis scale functions using the help function:

    help.search("scale_x", package = "ggplot2")

Scaling discrete axes is slightly different, but uses the same parameters

    ggplot(df, aes(x=Species, y=`Total length`)) + 
      geom_boxplot(outliers=F) 

To change the name of the axis, tick marks, and order:

    ggplot(df, aes(x=Species, y=`Total length`)) + 
      geom_boxplot(outliers=F) +
      scale_x_discrete(breaks=c("Acinetobacter baumannii","Klebsiella pneumoniae"),
                       limits=c("Klebsiella pneumoniae","Acinetobacter baumannii"),
                       labels=c("A. baumannii","K. pneumoniae"),
                       name="Assembly Species")

To choose which variables to display:

    ggplot(df, aes(x=Species, y=`Total length`)) + 
      geom_boxplot(outliers=F) +
      scale_x_discrete(limits=c("Acinetobacter baumannii"),
                       labels=c("A. baumannii"),
                       name="Assembly Species")
                       
#### Making figures with ggplot2 part IV: Themes and legends

In this section, we will go over even more ways to customize you figures, as well as their legends, using ggplot2's theme() function.  

For our example data, we will be using the same assembly QC table from the previous section:

    df <- read.delim("./data/quast_data.tsv", 
                     header=T, 
                     check.names=F,
                     stringsAsFactors=F,
                     sep="\t")

A. Built-in themes

ggplot2 has a number of built-in themes you can choose from for your figures. As you may have noticed, the default has a grey background and white  gridlines.

You can use the help function to search for the different types of themes available in ggplot2, or you can using the search bar in the help tab:

help.search("theme_grey", package="ggplot2")

We'll use the box plot from the last section to go over some of these 
built-in themes.

The classic dark-on-light ggplot2 theme:

    library(ggplot2)
    
    ggplot(df, aes(x=Species, y=`Total length`)) + 
      geom_boxplot(outliers=F) + theme_bw()

A theme with only black lines of various widths on white backgrounds:

    ggplot(df, aes(x=Species, y=`Total length`)) + 
      geom_boxplot(outliers=F) + theme_linedraw()

A theme similar to theme_linedraw() but with light grey lines and axes:

    ggplot(df, aes(x=Species, y=`Total length`)) + 
      geom_boxplot(outliers=F) + theme_light()

The dark cousin of theme_light(), with similar line sizes but a dark 
background:

    ggplot(df, aes(x=Species, y=`Total length`)) + 
      geom_boxplot(outliers=F) + theme_dark()

A minimalist theme with no background annotations:

    ggplot(df, aes(x=Species, y=`Total length`)) + 
      geom_boxplot(outliers=F) + theme_minimal()

A classic-looking theme, with x and y axis lines and no gridlines:

    ggplot(df, aes(x=Species, y=`Total length`)) + 
      geom_boxplot(outliers=F) + theme_classic()

A completely empty theme:

    ggplot(df, aes(x=Species, y=`Total length`)) + 
      geom_boxplot(outliers=F) + theme_void()

You can also install packages with other built-in themes
For example, one of my favorite themes is Dracula:

    library(ggDracula)
    
    ggplot(df, aes(x=Species, y=`Total length`, fill=Species)) + 
      geom_boxplot(outliers=F) +
      theme_dracula()

You can change basic elements of these themes using the base_size, base_family, base_line_size, and base_rect_size parameters:

    ggplot(df, aes(x=Species, y=`Total length`)) + 
      geom_boxplot(outliers=F) + theme_bw()
    
    base_size <- 17
    ggplot(df, aes(x=Species, y=`Total length`)) + 
      geom_boxplot(outliers=F) + 
      theme_bw(base_size=base_size,
               base_family="serif",
               base_line_size=base_size/22,
               base_rect_size=base_size/22)

Note: windowsFonts() can tell you the fonts available for you to choose from.  

There are other packages to increase the number of fonts to choose from e.g. extraFonts:

    windowsFonts()


B. Manually customizing plots with theme()

You can manually customize almost every non-data element of your plot using the theme() function. These elements include:

Line elements : axis lines, grid lines, plot panel border, etc.

    element_line() 

Text elements : plot title, axis titles, tick mark labels, legend title, etc.

    element_text() 

Rectangle elements : plot background, panel background, legend background, etc.

    element_rect()

These functions are used in concert with the theme() function to manually change the plot elements:

    ggplot(df, aes(x=Species, y=`Total length`)) + 
      geom_boxplot(outliers=F) +
      theme(panel.background=element_rect(fill="white",
                                          colour="purple",
                                          linewidth=1,
                                          linetype="solid"),
            panel.grid.major=element_line(linewidth=0.9,
                                          linetype="dashed",
                                          colour="blue"),
            panel.grid.minor=element_line(linewidth=0.7,
                                          linetype="dashed",
                                          colour="blue")) 

Alternatively, to remove these elements, we can use element_blank():

    ggplot(df, aes(x=Species, y=`Total length`)) + 
      geom_boxplot(outliers=F) +
      theme(panel.border=element_blank(),
            panel.grid.major=element_blank(),
            panel.grid.minor=element_blank())

Axes can also be formatted using theme() and element_text():

    ggplot(df, aes(x=Species, y=`Total length`)) + 
      geom_boxplot(outliers=F) + 
      scale_x_discrete(labels=c("A. baumannii","K. pneumoniae")) +
      labs(x="Assembly Species",
           y="Assembly Length (bp)",
           title="Species Assembly Lengths")
    
    
    ggplot(df, aes(x=Species, y=`Total length`)) + 
      geom_boxplot(outliers=F) + 
      scale_x_discrete(labels=c("A. baumannii","K. pneumoniae")) +
      labs(x="Assembly Species",
           y="Assembly Length (bp)",
           title="Species Assembly Lengths") +
      theme(plot.title=element_text(hjust=0.5),
            axis.title=element_text(family="serif"),
            axis.text=element_text(angle=45),
            axis.title.x=element_text(color="blue"),
            axis.text.x=element_text(size=12),
            axis.title.y=element_text(hjust=1),
            axis.text.y=element_text(angle=45),
            axis.ticks=element_blank())

There are many, many other parameters and functions for theme() that can be combined to customize your graph

C. Legends

Legends are included by default when a figure is plotted using ggplot.
For example, the scatter plot below includes a legend on the right,
and each point is colored as coral, green, blue, or purple:

    ggplot(df, aes(x=`Largest contig`, y=`Total length`, color=AMR)) + 
      geom_point()

We can change the position of the legend using the theme() function.
Options for legend.position include "none", "left", "right" (default), 
"bottom", "top", "inside":

    ggplot(df, aes(x=`Largest contig`, y=`Total length`, color=AMR)) + 
      geom_point() +
      theme(legend.position="top")
    
    ggplot(df, aes(x=`Largest contig`, y=`Total length`, color=AMR)) + 
      geom_point() +
      theme(legend.position="none")
    
    ggplot(df, aes(x=`Largest contig`, y=`Total length`, color=AMR)) + 
      geom_point() +
      theme(legend.position="inside")

Legend position can also be a numeric vector that include an x and y 
coordinate c(x,y), where x and y are values from 0-1:

    ggplot(df, aes(x=`Largest contig`, y=`Total length`, color=AMR)) + 
      geom_point() +
      theme(legend.position=c(1,1))
    
    ggplot(df, aes(x=`Largest contig`, y=`Total length`, color=AMR)) + 
      geom_point() +
      theme(legend.position=c(0.5,0.5))
    
    ggplot(df, aes(x=`Largest contig`, y=`Total length`, color=AMR)) + 
      geom_point() +
      theme(legend.position=c(0,0))

The element_text() function can be used with theme() to change the
legends text:

    ggplot(df, aes(x=`Largest contig`, y=`Total length`, color=AMR)) + 
      geom_point() +
      theme(legend.text=element_text(color="darkblue",angle=45),
            legend.title=element_text(face="bold", size="8"))
    
    ggplot(df, aes(x=`Largest contig`, y=`Total length`, color=AMR)) + 
      geom_point() +
      theme(legend.text=element_blank(),
            legend.title=element_blank())

Remember: Searching the help tab for a function like element_text() can show us its parameters:

    ?element_text()

The element_rect() function can be used with theme() to change the legend's color, fill, etc, just like the plot's background above:

    ggplot(df, aes(x=`Largest contig`, y=`Total length`, color=AMR)) + 
      geom_point() +
      theme(legend.background=element_rect(color="purple",
                                           fill="lightblue",
                                           linewidth=1,
                                           linetype=3))

#### Making figures with ggplot2 part V: Colors and saving your plots 

In this section, we will review how to customize the colors of your
figures and save figures to a file using ggplot2.  

For our example data, we will be using the same assembly QC table from the previous section:

    df <- read.delim("./data/quast_data.tsv", 
                     header=T, 
                     check.names=F,
                     stringsAsFactors=F,
                     sep="\t")

A. Brief review  

As discussed in previous sections, we can choose a single color for our plots, or we can color our plots by variables in our data set.  

Plotting with a single color is done outside aes():

    library(ggplot2)
    
    ggplot(df, aes(x=N50)) + 
      geom_histogram(bins=10, color="black", fill="lightgreen")  

If no color is specified within the geom function, ggplot2 will use black 
or grey by default.  

Coloring our plot by a variable in our data set is done within aes():

    ggplot(df, aes(x=N50, fill=Species)) +
      geom_histogram(bins=10)

If no color palette is given within aes() when coloring a plot by a variable in our data set, ggplot2 uses its built-in color palette by default.  

B. Hue, chroma, and value  

Hue, chroma, and value are part of the Munsell color system, which describes the properties of color.

https://munsell.com/color-blog/munsell-book-of-color-1929-hue-value-chroma/  

Hue is how we distinguish and name the colors present on the color wheel, chroma is the saturation of color, and value is the lightness (or darkness) of a color.  

The hue, chroma, and value of the colors in a plot can be changed using the scale_fill_hue() and scale_color_hue() functions.

    ggplot(df, aes(x=Species, y=`Total length`, color=Species)) + 
      geom_boxplot(outliers=F)

Hue is changed with the h parameter [0-360].  
For example, green is 120 degrees on the color wheel and purple is 270:

    ggplot(df, aes(x=Species, y=`Total length`, fill=Species)) + 
      geom_boxplot(color="black", outliers=F) +
      scale_fill_hue(h=c(120,270))
    
    ggplot(df, aes(x=Species, y=`Total length`, color=Species)) + 
      geom_boxplot(outliers=F) +
      scale_color_hue(h=c(120,270))

Chroma is changed with the c parameter (maximum value varies depending on a combination of hue and value):

    ggplot(df, aes(x=Species, y=`Total length`, fill=Species)) + 
      geom_boxplot(color="black", outliers=F) +
      scale_fill_hue(c=20)
    
    ggplot(df, aes(x=Species, y=`Total length`, fill=Species)) + 
      geom_boxplot(color="black", outliers=F) +
      scale_fill_hue(c=150)

Value is changed with the l (lightness) parameter [0,100]:

    ggplot(df, aes(x=Species, y=`Total length`, fill=Species)) + 
      geom_boxplot(color="black", outliers=F) +
      scale_fill_hue(l=90)
    
    ggplot(df, aes(x=Species, y=`Total length`, fill=Species)) + 
      geom_boxplot(color="black", outliers=F) +
      scale_fill_hue(l=10)  

C. Manually choosing colors  

Colors palettes can be chosen manually using scale_color_manual() and
scale_fill_manual(). Colors should be in hex code format. For example:

    cp2 <- c("6e0067","3ff0a1")
    
    cp4 <- c("d15124","002691","60c250","484e00")

There are many websites for generating color palettes. I prefer i want hue:  
http://medialab.github.io/iwanthue/

scale_fill_manual() can be used for figures like box plots, histograms, etc:

    ggplot(df, aes(x=Species, y=`Total length`, fill=Species)) + 
      geom_boxplot(color="black", outliers=F) +
      scale_fill_manual(values=cp2)

scale_color_manual() can be used for figures like line plots and scatter plots:

    ggplot(df, aes(x=`Largest contig`, y=`Total length`, color=AMR)) + 
      geom_point() +
      scale_color_manual(values=cp4)

ggplot2 also has grey color scale functions, scale_fill_grey() and 
scale_color_grey():

    ggplot(df, aes(x=Species, y=`Total length`, fill=Species)) + 
      geom_boxplot(color="black", outliers=F) +
      scale_fill_grey()
    
    ggplot(df, aes(x=`Largest contig`, y=`Total length`, color=AMR)) + 
      geom_point() +
      scale_color_grey()
    
    ?scale_fill_grey()

Color gradients for continuous variables can be set using scale_color_gradient() and scale_fill_gradient():

    ggplot(df, aes(x=`Largest contig`, y=`Total length`, color=`N50`)) + 
      geom_point() +
      scale_color_gradient()

We can use the high and low parameters to choose either end of gradients, and ggplot2 will automatically create a gradient using those colors:

    ggplot(df, aes(x=`Largest contig`, y=`Total length`, color=`N50`)) + 
      geom_point() +
      scale_color_gradient(low="6e0067", high="3ff0a1")
    
    Additionally, scale_fill/color_gradient2() can be used to create a color 
    gradient with a chosen middle color aka a diverging color gradient:
    
    ggplot(df, aes(x=`Largest contig`, y=`Total length`, color=`N50`)) + 
      geom_point() +
      scale_color_gradient2(low="6e0067", high="3ff0a1", mid="grey",
                            midpoint=mean(df$N50))

D. Color palette modules  

There are many color palette modules for R that have been written. Some examples include:

    library(RColorBrewer)
    https://r-graph-gallery.com/38-rcolorbrewers-palettes.html
    
    ggplot(df, aes(x=`Largest contig`, y=`Total length`, color=AMR)) + 
      geom_point() +
      scale_color_brewer(palette="Set1")
    
    library(viridis)
    https://cran.r-project.org/web/packages/viridis/vignettes/intro-to-viridis.html
    
    ggplot(df, aes(x=`Largest contig`, y=`Total length`, color=AMR)) + 
      geom_point() +
      scale_color_viridis(option="plasma", discrete=T)
    
    library(ggDracula)
    https://github.com/dracula/ggplot2
    
    ggplot(df, aes(x=`Largest contig`, y=`Total length`, color=AMR)) + 
      geom_point() +
      scale_color_dracula(discrete=T)

E. Saving your plot  

The easiest way to save your plot is using ggsave().  
ggsave() will save the last figure you plotted to a file by default, or you can supply it a variable containing a plot:

    ?ggsave
    
    ggsave("my_plot.png",
           path="./figures/",
           width=5,
           height=5,
           units="in",
           dpi=300)
    
    my_plot <- ggplot(df, aes(x=`Largest contig`, y=`Total length`, color=AMR)) + 
      geom_point() +
      scale_color_viridis(option="plasma", discrete=T)
    my_plot
    
    ggsave("my_plot.png",
           plot=my_plot,
           path="./figures/",
           width=5,
           height=5,
           units="in",
       dpi=300)

## General Bioinformatic Terms

Figures to be included: 
None

### Bioinformatics
This discipline is involved in the collection, analysis, and storage of complex biological data, including, but not limited to genetic data. The field combines computer science, statistics, and several aspects of biology to be able to understand highly complex data.

### AMD (Advanced Molecular Detection)
This commonly may mean any form of sequencing or high-level molecular technology. There is an Office of Advanced Molecular Detection (OAMD) at CDC that provides support and input on many cross-cutting areas using advanced technologies.

### Genomics

* **Gene** – sequence of DNA that encodes a region for a molecule (ie protein or enzymes) with function.

* **Genotype vs Phenotype** – **Genotypes** are the genetic make-up of an individual. **Phenotypes** are the physical traits and characteristics of an individual and are influenced by their genotype and the environment.

* **Mobile elements** – Sequences of DNA that have the ability to move from one organism to another, move into different locations in a genome or change the copy number in the bacteria. These element include plasmids, bacteriophages and transposable elements.

* **Mutation Rates** – The rate in which a single nucleotide is replaced by a different nucleotide.

Recombination – rearrangement of genetic material. Both prokaryotes and eukaryotes can perform recombination.

* **Operon** – It is a genetic regulatory system found in bacteria and their viruses in which genes coding for functionally related proteins are clustered along the DNA. This feature allows protein synthesis to be controlled coordinately in response to the needs of the cell. A typical operon consists of a group of structural genes that code for enzymes involved in a metabolic pathway, such as the biosynthesis of an amino acid. These genes are located contiguously on a stretch of DNA and are under the control of one promoter (a short segment of DNA to which the RNA polymerase binds to initiate transcription). A single unit of messenger RNA (mRNA) is transcribed from the operon and is subsequently translated into separate proteins.

* **Structural variants (SVs)** – DNA sequence variants that are 50bp or larger, including insertions, deletions, inversions, duplications and translocations.

### Programming Languages

* **BASH / Shell Script** – A programming language that is directly used by the Linux operating system. It allows for direct control of the operating system functions.

* **Command line / Command based** – The command line allows the user to interact with their computer without graphical user interface (GUI) or mouse. The command line is essential to perform bioinformatics analysis. It allows the user to manipulate files and programs in ways that are not possible using a GUI.

* **Linux** – An operating system much like Windows or OSX. The field of bioinformatics relies heavily on Linux-based computers and software. Although some bioinformatics programs can be compiled to run on Mac OS X and Windows systems, many require the Linux environment to run properly.

* **Python** – Python is a popular programming language object often used for scientific computing. The Biopython utilize python-based software for bioinformatics research, thereby creating high quality reusable modules and scripts.

* **PERL** – Another programming language similar to Python.

### Sequencing Instruments and Chemistry

* **PacBio** –  A single molecule real time (SMRT) sequencing developed by Pacific Biosciences, also referred as PacBio sequencing. Unlike second generation sequencing, PacBio sequences each base-pair individually. Currently, this method is widely used to study larger genomes, transcriptome metagenomics and epigenetics.

* **Pyrosequencing** –  In pyrosequencing, the sequencing reaction is monitored through the release of the pyrophosphate during nucleotide incorporation. A single nucleotide is added to the sequencing chip which will lead to its incorporation in a template dependent manner. This incorporation will result in the release of pyrophosphate which is used in a series of chemical reactions resulting in the generation of light. Light emission is detected by a camera which records the appropriate sequence of the cluster. Any unincorporated bases are degraded by apyrase before the addition of the next nucleotide. This cycle continues until the sequencing reaction is complete.

* **Paired-end sequencing** – Sequencing both ends of the DNA fragment and generate high quality sequence data. It’s a simple work flow allows generation of unique ranges of insert sizes.

* **Long read sequencing** – Third generation sequencing also known as long read sequencing (LRS). LRS allows for the retrieval of much longer (>10,000bp) sequencing reads than widely-used short read sequencing systems (75-300bp). Long-read sequencing (LRS) has become increasingly important due to its strengths in resolving complex DNA regions as well as in determining full-length RNA molecules. Two important LRS technologies have been developed during the past few years, including single-molecule, real-time sequencing by Pacific Biosciences, and nanopore sequencing by Oxford Nanopore Technologies.

* **Short read sequencing** – Next generation sequencing also known as short read sequencing. The technology utilizes highest output platform continue to have relatively short read lengths on the order of 35-300 bases per read. The amazing increase in data output and decrease in cost per base sequenced has been driven primarily short-read sequencing technologies such as the Illumina and Ion Torrent platforms.

* **Massively parallel sequencing** – Massively parallel sequencing (MPS) technology, also referred to as next-generation sequencing, is a high-throughput approach to DNA sequencing in which miniaturized, parallelized platforms are used for sequencing 1 million to 43 billion short reads per instrument run. Next-generation sequencing (NGS) is transforming the landscape of clinical microbiology and public health laboratories. The applications of NGS are wide-ranging and include whole-genome sequencing, microbiome analysis/metagenomics, transcriptome profiling, infectious disease diagnosis, pathogen discovery, and public health surveillance.

* **Base Calling** – Base calling is the process of assigning nucleotides or bases (ATGC) with chromatogram peaks. Next generation sequencing platforms, which use fluorescently labeled reversible terminators have a unique color for each base. These are incorporated in to the complementary strand of the DNA template and captured with a sensitive CCD camera. These images are processed into signals which are used to infer the order of nucleotides also referred as base calling. The accuracy is, measured by a Q score (Phred quality score), a common metric to assess the accuracy of a sequencing run.

* **Adapter** – Oligonucleotides bound to 5’ and 3’ end of each fragment in a sequencing library. Adapters include platform-specific sequences for fragment recognition by the sequencer. For example, the P5 and P7 sequences enable library fragments to bind to the flow cells of Illumina platforms.

* **Barcode sequences** – Multiplex sequencing allows large numbers of libraries to be pooled and sequenced simultaneously during a single run on a high-throughput Illumina NextGen sequencer. Individual "barcode" sequences are added to each DNA fragment during next-generation sequencing (NGS) library preparation so that each read can be identified and sorted out based on the fingerprinting of the genome prior to final data analysis.

* **Sanger Sequencing** – DNA sequencing method that relies on a primer to bind to the DNA sequence of interest to amplify the region of interest, sequences a single DNA fragment.

### Bioinformatic Analysis

* **ANI (average nucleotide identity)** – Provides a measure of how similar two genomes are at the nucleotide level.

* **Coverage** – number of reads that are aligned at a specific nucleotide.

* **Contig (contiguous DNA)** – Sequences of DNA that have been assembled together as the result of overlapping sequences into a consensus sequence and resulting in a contiguous sequence.

* ***De novo*** **assembly** – Assembly of sequencing reads without using a reference sequence as a guide

* **DNA Sequence Analysis**

  * **MLST (Multi Locus Sequence Typing)** – Traditionally used 6-12 housekeeping genes and Sanger sequencing to identify gene variants and alleles, which can be used to generate sequence types (ST), standardized allele schemes.
 
  * **cgMLST (Core genome MLST)** – Examines only the genes that are shared among all of the strains to assign alleles, these genes are shared by the majority of the strains within a genus.
  
  * **wgMLST (whole genome MLST)** – Examines all genes within the genome to assign allele codes to an organism, examined on a gene by gene basis and can be either the whole gene or part of the gene to form the locus, variants within the locus are given new allele codes to generate wgMLST types.

  * **Consensus** – Sequence of nucleotides that represents the most commonly found base pair at a specific position, identified by aligning the raw reads.
 
* **Reference assembly** – Mapping reads to a reference genome in order to assembly the reads into contigs or closed genomes.

  * **Reference genome** – A consensus sequence of DNA for an organism.

  * **Variants** – Sequences of DNA that differ at specific positions when the sequences are aligned.

  * **Alleles** – Variant of a sequence, variant does not have to affect the phenotype.

  * **SNP (single nucleotide polymorphism)** – A nucleotide position that can be used to discriminate strains in a population.

  * **hqSNP (High quality SNP)** – Utilizes a program such a lyve-SET to identify SNPs that have at least 20X coverage and uses a high quality reference genome.

  * **Query sequence** –  BLAST (Basic Local Alignment Search Tool) uses statistical methods to compare a DNA or protein input sequence (“query sequence”) to a database of sequences (“subject sequences”) and return those sequences that have a significant level of similarity to the query sequence.

* **File Types**

    * **FASTQ file** – Contains the raw sequencing data, contains the NGS read data including both the DNA sequences and the quality sequencing information for each read, each read has the read ID, the base calls, additional information and sequencing quality metrics.

    * **FASTA file** – Contains DNA/RNA or protein sequences, “>” denotes the header/sequence identifier.

    * **SAM (Sequence Alignment/Map) file** – Contains the alignment of reads to a reference genome.

    * **BAM file** – Compressed binary version of a SAM file.
  
* **Filtering** – Pre-processing of raw reads before assembly to remove any reads that do not meet a specified quality parameters.

* **Gene or sequence annotation** – Sequence annotation is the process of marking specific regions or sites of interest in the protein sequence, such as post-translational modifications, binding sites, enzyme active sites, local secondary etc. Annotation may be defined as the part of genome analysis that is customarily performed before a genome sequence is deposited in GenBank and described in a published paper.

* **k-mer** – K-mers are often used in computational genomics. K-mer refers to all the possible sub-sequences of a defined length obtained from a set of sequence information.

* **Metagenomics** – The study of complex bacterial communities to examine diversity of organisms at various taxonomic levels. Sequencing can be performed using 16S primers (16S sequencing) or by sequencing all DNA in a sample (shotgun sequencing) to identify genes present and identification of organisms

* **Multiple sequence alignment** – Multiple Sequence Alignment (MSA) is generally the alignment of three or more biological sequences (protein or nucleic acid) of similar length. In contrast, Pairwise Sequence Alignment tools are used to identify regions of similarity that may indicate functional, structural and/or evolutionary relationships between two biological sequences.

* **NCBI (National Center for Biotechnology Information)** – Part of the National Laboratory of Medicine and National Institute of health. The Entrez Global Query Cross Database search system is widely adopted by NCBI for array of nucleotide and protein sequences, protein structures, PubMed, taxonomy, whole genome etc.

* **N50** – A weighted average length; specifically, the N50 length is the length such that 50% of the genome has been assembled into contig or scaffold sequences of this length or longer.

* **Pipeline** – The chain of processing data and moving files through different processes or functions to produce the desired files and results, also referred to as a workflow.

* **Proteomics** – The study of all the proteins in a system and their interactions, structure and composition.

* **Q Score** – the quality score is the probability of an incorrect base call; Q30: 1 in 1000 times incorrect, thus, each nucleotide is 99.9% accurate.

* **Reading frame and Open reading frame (ORF)** –  An ORF is a sequence of DNA that starts with start codon “ATG” and ends with any of the three termination codons (TAA, TAG, TGA). Depending on the starting point, there are six possible ways (three on forward strand and three on complementary strand) of translating any nucleotide sequence into amino acid sequence according to the genetic code. These are called reading frames.

* **Reads** – Fragments of sequenced DNA base pairs that are generated during sequencing, the raw data from a sequencing machine

* **Sequence Similarity** – It is a method of searching sequence databases by using alignment to a query sequence. Similarity of two sequences refers to the degree of match between corresponding positions in sequence.

* **Source Control / Version Control** – Tracking of changes made to files or authorship to be able to recall previous versions. Github is a way to keep track of changes made to files and identify who made the changes.

## Common Phylogenetic Terms

* **Phylogenetic tree** – a branching diagram or dendrogram illustrating the evolutionary relationships among species.

* **Bootstrapping** – Bootstrapping is a statistical resampling technique that is often used to increase the confidence that the inferred tree is correct.

* **Outgroups** – When using distance matrix methods, it is highly recommended to include at least one distantly related sequence for the analysis. This is a negative control. The outgroup should appear near the root of the tree and should have a longer branch length than any other sequence.

Bootstrap values: statistical analysis to estimate the error in sampling, allows for approximating the distribution through resampling the data set. The bootstrapping value provides the confidence values for the phylogenetic relationships

* **Cladogram** – A diagram, also referred to as phylogenetic tree, that shows relationship between organisms and are not evolutionary in nature

* **Chronogram** – phylogenetic trees that specifically deal with time

* **Rooted VS. unrooted trees** – a rooted tree will have an outgroup or a unique node that will be designated as the most recent common ancestor for all of the other nodes in the tree, while an unrooted tree will only show relatedness of the strains

* **Nodes** – can be either the external nodes which represent the sequences or taxa or internal nodes which are hypothetical sequences representative of a common ancestor

* **Branch length** – the branch length is indicative of the amount of genetic change that has occurred, most branch lengths are drawn to scale by using the number of nucleotide substitutions per site  

* **Character based** – use the sequence alignments directly to generate trees

  * **Maximum parsimony (MP)** – This method tries to create a phylogeny that requires the least evolutionary change, builds a phylogenetic tree based on the smallest number of evolutionary changes, this method will compare a number of trees and choose the one with the lease number of evolutionary steps
 
  * **Maximum-likelihood (ML)** – ML uses a statistical approach to infer a phylogenetic tree. ML is well suited for the analysis of distantly related sequences but is computationally expensive and thus not that well suited for larger input data, phylogenetic tree will be built based on a specific model specified, it will take into account the statistical likelihood of one sequence being converted into another

* **Distance-based** – transform the sequence alignments into distance matrixes  

  * **Neighbor-Joining method** – a distance based method that chooses the closest neighbor, does not assume that all taxa are equidistant from the root
  
  * **UPGMA (Unweighted Pair Group Method with Arithmetic Mean)** – A simple clustering method that assumes a constant rate of evolution (molecular clock hypothesis). It needs a distance matrix of the analyzed taxa that can be calculated from a multiple alignment, this method will build phylogenetic trees based off of a distance matrix, it will assume to start building the tree by clustering the two most related taxa and then sequentially add the next related taxa to the tree
