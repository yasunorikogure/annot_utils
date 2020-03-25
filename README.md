# annot_utils2

[![Build Status](https://travis-ci.org/friend1ws/annot_utils2.svg?branch=master)](https://travis-ci.org/friend1ws/annot_utils2)
[![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![PyPI](https://img.shields.io/pypi/v/annot-utils2.svg?)](https://pypi.python.org/pypi/annot-utils2)


## Introduction
`annot_utils2` is yet another annot_utils (software for generating tabix-indexed annotation files, which can be shared by other softwares by yuichi shiraishi)

- Gencode dabase is fixed to Gencode19.
- Annotation style is updated

## Dependency

### Python packages

`pkg_resources`

## Software

[hstlib](http://www.htslib.org)

## Install

``annot_utils2`` is available through pypi. 
To install, type:
```
pip install annot_utils2 
```
When you are not the root user, you may want to type:
```
pip install annot_utils2 --user
```

Alternatively, install from the source code:
```
wget https://github.com/friend1ws/annot_utils2/archive/v0.3.0.tar.gz
tar xzvf v0.3.0.tar.gz 
cd annot_utils2-0.3.0
python setup.py build install --user
```

This package has been tested on Python 2.7, 3.5, 3.6.

## Update databse
Currently, `annot_utils2` already store annotation files from [UCSC genome browser](https://genome.ucsc.edu) and several other sources upon installation.
If you want to update the annotation files:
```
cd annot_utils2/resource
bash prep_data.sh
```
Then, install the software from the source code.

## Commands

### gene

Generate gene annotation bed flies indexed by tabix.

```
annot_utils2 gene [-h] 
                 [--gene_model {refseq,gencode}] [--grc]
                 [--genome_id {hg19,hg38,mm10}] [--add_ref_id]
                 gene.bed.gz
```


### exon

Generate exon annotation bed flies indexed by tabix.


```
annot_utils2 exon [-h] 
                 [--gene_model {refseq,gencode}] [--grc]
                 [--genome_id {hg19,hg38,mm10}] [--add_ref_id]
                 exon.bed.gz
```


### coding

Generate regional (coding, intronic, 5'UTR, 3'UTR and so on) annotation bed flies indexed by tabix.

```
annot_utils2 coding [-h] 
                   [--gene_model {refseq,gencode}] [--grc]
                   [--genome_id {hg19,hg38,mm10}] [--add_ref_id]
                   coding.bed.gz
```

### junction

Generate annotated splicing junction bed files indexed by tabix.

```
annot_utils2 junction
usage: annot_utils2 junction [-h] 
                            [--gene_model {refseq,gencode}] [--grc]
                            [--genome_id {hg19,hg38,mm10}] [--add_ref_id]
                            junction.bed.gz
```

### boundary


Generate exon intron boundary annotation files index by tabix.

```
annot_utils2 boundary [-h] 
                     [--genome_id {hg19,hg38,mm10}] [--grc]
                     [--donor_size donor_size]
                     [--acceptor_size acceptor_size]
                     boudary.bed.gz
```

