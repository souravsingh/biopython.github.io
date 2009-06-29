---
title: Ace contig class
permalink: wiki/Ace_contig_class
layout: wiki
---

This page describes the **Contig** class used in **Bio.Sequencing.Ace**
to hold all of the imfomation about a single contig recored in an Ace
file.

Summary Diagram
---------------

![](Contig_class.png "Contig_class.png")

Examples
--------

``` python
#Start my parsing a file to get some contigs 
>>>from Bio.Sequencing import Ace
>>>ace_gen = Ace.parse(open("contig1.ace", 'r')) # from Tests/Ace/contig1.ace
>>>contig = ace_gen.next()

# just the consensus sequence
>>>contig.sequence
'aatacgGGATTGCCCTAGTAACGGCGAGTGAAGCGGCAACAGCTCAAATTTG......'
# assembler designated quality for each base in the consensus
>>>contig.quality
[0, 0, 0, 0, 0, 0, 22, 23, 25, 28, 34, 47,...]

# Ace files also contain information on the reads that make up the consensus.
# Information about the reads are in two lists, "reads" and "af"

# so, to get read sequence for every read in a contig
# and that reads position in its contig
>>>for i in range(len(contig.reads)):               
...     contig.af[i].padded_start           
...     contig.reads[i].rd.sequence
...                                
'tagcgaggaaagaacccaacaGg...'
-14  
'aatacgGGATTGCCCTagtaacG...'
1
```