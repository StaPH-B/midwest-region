---
layout: page
title: Genomic Relatedness
description: A primer on how genomic sequence data can be use to determine how organisms might be related.
guide_number: 2
---

# Methods For Comparing Genomic Relatedness

## Learning Objectives

### By the end of this presentation you should  be able to:
1. Name and describe three standardized methods for comparing genomic relatedness
2. Name and describe two non-standardized methods for comparing genomic relatedness
3. Name the advantages and disadvantages of using standardized vs non-standardized methods for comparing genomic relatedness

## Background Definitions
- **Genome:** The entire set of DNA (bases) instructions found in a cell
- **Genomic relatedness:** How closely related ≥2 genomes are
- **Allele:** One of two or more versions of a DNA sequence (a single base or group of bases) at a given genomic location
- **Locus:** Specific positions in the genome where genes or genetic markers are located
- **Core genome:** Genes present in nearly all (95-99%) isolates of a given species or a subset of that species
- **Accessory genome:** Genes present in only certain members of a given species or a subset of that species
- **Single nucleotide polymorphism (SNP):** A genomic variant at a single base position in the genome or DNA sequence. SNPs are identified as differences from a reference sequence or as differences from other isolates.

### SNPS
In the figure a SNP occurs at position nine and fifteen in the DNA sequence. Isolate 1 has a ‘A’ nucleotide, while the reference has a ‘T’ nucleotide. SNP combinations and total number of SNPs can be used to identify
relatedness between isolates.

SNPs accumulate over time, which allows us to assess relatedness between individuals. In general, the more SNP differences two members of a species have, the less likely it is that they are related. Conversely, if two
members of a species have very few SNP differences, the more likely it is that they are related.

#### Not all SNPs are equal, some may not even be included!
Our ability to accurately identify SNPs is limited by the sequencing technology we use and how we analyze our sequencing data. Sequencing technologies have associated error rates, which can introduce false SNPs into
our sequence data. Additionally, bioinformatic workflows differ in the methods or quality metrics they use to confidently identify SNPs. While many organizations have defined best practices for identifying SNPs, there is no current consensus on how to confidently identify SNPs in sequencing data. The SNPs identified between isolates can vary greatly from workflow to workflow, so SNP results should always be evaluated with additional analyses.

## Methods for Determining Relatedness

Methods for determining genomic relatedness fall into two major categories:
1. Standardized
2. Non-standardized

### Standardized methods

#### Multilocus sequence typing (MLST)

##### It’s all about the loci, but how many is multi?
Originally multi-locus sequence typing (MLST) was devised as a way to characterize DNA sequences. Before next-generation sequencing (NGS) became available, this method was developed to characterize and identify isolates by PCR amplifying and sequencing a small portion of 7 - 8 housekeeping genes found within every organism of that genus/species. These genes are well conserved (i.e. they accumulate very few mutations over time), so it is possible to identify and type sequences using combinations of mutations. MLST works well for tracking organisms on a global level, but it is not very useful for outbreak investigations, because it uses such a small portion of the genome that doesn’t change very often.

#### Core genome multilocus sequence typing (cgMLST)

#### Whole-genome multilocus sequence typing (wgMLST)

#### Advantages of standardized methods

#### Disadvantages of standardized methods

#### Examples of standardized methods

##### PubMLST

##### Bionumerics

### Non-Standardized Methods

#### SNP analysis

#### Core genome analysis

#### Advantages of non-standardized methods

#### Disadvantages of non-standardized methods

#### Examples of non-standardized methods
