---
title: Interface Analysis
permalink: wiki/Interface_Analysis
layout: wiki
---

### Description

The Interface module integrated in biopython provides an easy and
friendly way to extract and analyse interface from PDB complexes.
Different information are calculated and provided with the extraction of
the interface: - polar/apolar/charged residues distribution - buried
surface area

Developed during the Google Summer of Code 2011 by Mikael Trellet, this
module is still not available in the official repository of Biopython.
Nevertheless you can find the code (open-source) at the current link:
[GitHub
source](https://github.com/mtrellet/biopython/tree/interface_analysis)
In order to be relevant and complete, the Interface module works in
parallel with extended residues, a subclass of residue created during
the same period and also available at the previous link.

### Requirements

The main part of the Interface analysis module requires only a stable
installation of Biopython and python 2.7. A more precise definition of
the interface can be done using the NACCESS module present in Biopython
but require a stable version of Naccess (available in
[NACCESS](http://www.bioinf.manchester.ac.uk/naccess/)).

### How to use

Extraction of an interface is done from a complex PDB you have to parse

`from Bio.PDB import InterfaceBuilder`  
  
`parser=PDBParser()`  
`structure=parser.get_structure('test', '/home/directory/of/your/PDB/test.pdb')`