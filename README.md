# DROPA v2.0

# Installation
1) Python:

DROPA core is written in Python 3.5 You can install Python directly from the Console with the command:
	
	sudo apt-get install python3

Install Pip to get the packages that DROPA needs for running.

	sudo apt install python3-pip

Here is the list of required packages:
	
  - numpy(v. 1.16.1)
  - pandas(v. 0.24.1)
  - tqdm(v. 4.31.1)
  - intervaltree(v. 3.0.2)
  - matplotlib(v. 3.0.3)
  - upsetplot(v. 0.2.1)
  - argparse(v. 1.4.0)
	
To install them:

	pip3 install numpy pandas tqdm intervaltree matplotlib upsetplot argparse


2) Bedtools

bedtools is required specifically for the creation of random data. To install bedtools:

	sudo apt-get install bedtools
Bedtools shuffle requires a genome size file structured as follow:
	
	<ChromosomeName><TAB><ChromosomeSize>
	
For hg19 this file is provided.

  
# Usage
DROPA was tested on a machine running Ubuntu OS (vers. 16.04 LTS and 18.04 LTS)

As input, DROPA requires four files, which are:

●	A file containing query peak locations in Browser Extensible Data (BED) format (BED6 and BED12 are supported);

●	A reference set containing information about genes features (5’UTR, 3’UTR, CDE, etc.) in BED format and a gene reference in BED format; Reference sets for hg19 (Ensembl, UCSCgenes and RefSeq) are provided. Other reference set can be created downloading data from UCSC Table Browser (https://genome.ucsc.edu/cgi-bin/hgTables).

●	A 2-column gene expression table  containing the name of each gene in the refernce set and its expression value (FPKM, TPM, microarray expression value, etc.). If this file is not provided, then DROPA skips the gene expression evaluation and annotates each query peak to the gene with the largest overlap.


To test the program try:

	python DROPA_v2.0.py Test.DRIP_peaks.bed -a RefSeqAnnotation/ -o TEST_out -rnaseq Test_RefSeq_Expression -shuffle 2 
