## 2021-10-28
# Classification of the aldo-keto reductase gene superfamily in plants
To classify plant ado-keto reductase-domain (PF00248) containing proteins via blastp search using RefPlantAKRs.fa dataset

#❗️Before starting the analysis, make sure that you instal seqkit, blast+ and datamash.

To install seqkit see https://bioinf.shenwei.me/seqkit/download/ or https://anaconda.org/bioconda/seqkit

To install blast+ see https://blast.ncbi.nlm.nih.gov/Blast.cgi?PAGE_TYPE=BlastDocs&DOC_TYPE=Download or https://anaconda.org/bioconda/blast

To install datamash see https://www.gnu.org/software/datamash/download/ or https://anaconda.org/bioconda/datamash

#❗️create a directory and copy your input_ProteinSequence_file, RefPlantAKRs.fa, and PlantAKRClassification.sh in the directory.

#❗️make sure that the fasta header of your input_ProteinSequence_file contain only sequence id and no other attributes (see TaAKRs.fa).

#❗️check line 26 in the PlantAKRClassification.sh file and input the name of your input_ProteinSequence_file. 

#❗️Depending on the seqkit, blast+ and datamash environment, run the script file.

#❗️once everything is set, just call the script ./PlantAKRClassification.sh in the terminal. You will get the final output within few seconds (or in a minute, based on your query size) if everything is good.

#❗️for any queries contact: Dr. Panneerselvam Krishnamurthy (pselva7@gmail.com)
