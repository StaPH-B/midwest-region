---
layout: page
title: Common Phylogenetic Terms
description: A glossary of terms commonly used in Phylogenetics
resource_number: 3
---

# Common Phylogenetic Terms

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
