---
layout: default
---

## Basic analysis of sequencing data

#### The Bioinformatic Pipeline
------------

Bioinformatic pipelines process raw sequencing data to produce meaningful results that can be interpreted by the lab. Like many benchtop assays, pipelines are tailored to answer specific questions like detecting resistance mechanisms or identifying outbreak strains. This overview will walk through the general process that some bioinformatic pipelines take to process raw sequence information into actionable data.


##### Quality
The first phase of working with raw sequencing reads is ensuring high quality basecalls. Here the phrase garbage in / garbage out holds true. In the previous section, fastq files had both the basescalls and the quality or likelihood of a correct basecall. Before using this information, most pipelines will trim the reads where the quality of the basecall drops below a specific threshold (usually around a phred score of 30).

There are other quality control measures that can also be used including removing the sequencing adapters from the ends of the reads or removing potentially contaminating sequences.

##### Reference Mapping or *de novo* Assembly
After cleaning the raw sequencing reads, often the next step is to use the reads to generate a representative picture of the genome. The two major methods of reconstructing a genome are mapping the reads to a reference or using overlaps to generate a *de novo* assembly.

**Reference Mapping**
Reference mapping is a process of selecting a reference sequence and then mapping the raw reads to the reference. In this approach it's important to select a reference that is most closely related to the organism being sequenced. Choosing a reference that is too distant can result a less reads being mapped and therefore less sequence information being used to generate the genomic sequence.

![https://galaxyproject.github.io/training-material/topics/sequence-analysis/images/mapping/mapping.png](https://amd-midwest.github.io/bioinfo_course/images/mapping.png "Reference Mapping")

** *De novo* Assembly**
The *de novo* assembly process uses overlapping portions of the sequencing reads to generate contiguous sequences also known as contigs. The advantage of this approach is that it is independent of a reference sequence. The final output is the best representation of the sequencing reads. However, repetitive regions of the genome can cause issues with the process of generating contiguous sequence.

![https://people.eecs.berkeley.edu/~penpornk/cs267.spr15/hw3/assembly.png](https://amd-midwest.github.io/bioinfo_course/images/assembly.png "de novo assembly")

##### Comparison
Once a genomic sequence or genomic contigs have been generated these can be used as the input for a vast number of different tools and analyses. For example the resistance detection tool [Abricate](https://github.com/tseemann/abricate) searches through the contigs to find known antimicrobial resistance mechanisms.
