# VoronaGasyCodes
VoronaGasyCodes is a publicly accessible, actively curated database of mitochondrial barcodes for Malagasy birds. It was created to facilitate species identification for researchers in Madagascar using metabarcoding or traditional sampling methods. This initial database, introduced in our ADD_JOURNAL paper, includes sequence data from ??? vouchered museum specimens for six mitochondrial genes: 12S, 16S, COI, Cytb, ND2, and ND3. 

## Usage
Users with BLAST experience should simply download the latest VoronaGasyCodes.fasta file and create a local BLAST database with their desired settings. The METADATA.csv file provides information on each specimen.

```
# create conda environment
conda create -n mada_blast
conda activate mada_blast

# install blast+
conda install bioconda::blast

# create directory and download VoronGasyCodes
mkdir VoronGasyCodes
cd VoronGasyCodes
wget https://github.com/jdylanmaddox/VoronaGasyCodes/blob/master/VoronGasyCodes.fasta

# create blast+ database
makeblastdb -in VoronaGasyCodes.fasta -dbtype nucl -out VoronaGasyCodes

# blast VoronaGasyCodes database
blastn -query RNP_NGS_aves_seq.fasta -db VoronaGasyCodes -outfmt 6 -num_threads 4 -out example_BLAST_results.txt -max_target_seqs 5 
```

If you'd prefer a GUI option, Geneious can perform local blast. users can download the lastest VoronaGasyCodes.geneious file and ADD INSTRUCTIONS


## Future Plans
Our future plans include expanding the database with endemic species not included in the initial version and to add samples from multiple geographic locations for species already represented. While our goal is to establish a comprehensive database backed by vourchered museum specimens, we recognize the utility of sequence data from other sources (eDNA, iDNA, etc.). Consequently, we invite researchers working in Madagascar to submit their own data for inclusion to the database. For submission inquiries, please contact Dylan Maddox or Sushma Reddy.

## Citation
If you use VoronaGasyCodes in your research, please cite our paper: ADD_REFERENCE.

## Contact Information
Please use our GitHub issue tracker to provide feedback, ask questions, or report errors.
