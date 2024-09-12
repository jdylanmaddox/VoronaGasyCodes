# VoronaGasyCodes
VoronaGasyCodes is a publicly accessible, actively curated database of mitochondrial barcodes for Malagasy birds. It was created to facilitate species identification for researchers in Madagascar using metabarcoding or traditional sampling methods. This initial database, introduced in our ADD_JOURNAL paper, includes sequence data from ??? vouchered museum specimens for six mitochondrial genes: 12S, 16S, COI, Cytb, ND2, and ND3. 

## Usage
Users with BLAST experience should simply download the latest VoronaGasyCodes.fasta file and incorporate it into their workflows. Information about each specimen can be found in  METADATA.csv.

For those with limited or no BLAST experience, here are two simple approaches to use VoronaGasyCodes, one via the command line interface (CLI) and the other through a graphical user interface (GUI).


### 1) BLAST+ in a conda environment 
Note, conda is not required but it's usually eaiser. See the [Conda Documentation](https://conda.io/projects/conda/en/latest/index.html) for help installing and using conda. 

- create a conda environment
```
conda create -n vgc_blast
conda activate vgc_blast
```
- install BLAST+
```
conda install bioconda::blast
```
- create new directory and download VoronaGasyCodes
```
mkdir VoronGasyCodes
cd VoronGasyCodes
wget https://github.com/jdylanmaddox/VoronaGasyCodes/blob/master/VoronGasyCodes.fasta
```
- create local BLAST+ database
```
makeblastdb -in VoronaGasyCodes.fasta -dbtype nucl -out VoronaGasyCodes
```
- perform BLAST+ search using VoronaGasyCodes  
```
blastn -query RNP_NGS_aves_seq.fasta -db VoronaGasyCodes -outfmt 6 -num_threads 4 -out example_BLAST_results.txt -max_target_seqs 5 
```

### 2) Geneious
The paid version of Geneious can perform local or custom blast searches. Simply download the VoronaGasyCodes.fasta file, import it to Geneious, and follow these
[instructions](https://help.geneious.com/hc/en-us/articles/360044627372-How-can-I-BLAST-against-my-own-sequences-or-a-database-that-isn-t-part-of-NCBI). For the "Add BLAST Database" step, simply select the VoronaGasyCodes file you importaned.

## Future Plans
We plan to expand the database with endemic species not included in our initial version as well as samples from multiple geographic locations for species already represented. While our goal is to establish a comprehensive database backed by vourchered museum specimens, we recognize the utility of sequence data from other sources (eDNA, iDNA, etc.). Consequently, we invite researchers working in Madagascar to submit their own data for inclusion to the database. For submission inquiries, please contact Dylan Maddox or Sushma Reddy.

## Citation
If you use VoronaGasyCodes in your research, please cite our paper: ADD_REFERENCE.

## Contact Information
Please use our [GitHub issue tracker](https://github.com/jdylanmaddox/VoronaGasyCodes/issues) to provide feedback, ask questions, or report errors.
