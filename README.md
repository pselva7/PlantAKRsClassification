## 2021-10-29
# Classification of the aldo-keto reductase (AKR) gene superfamily in plants
Aldo-keto reductase-domain (PF00248) containing proteins (AKRs) are NAD(P)(H)-dependent oxidoreductases of a multigene superfamily that mediate versatile functions in plants ranging from detoxification, metal chelation, potassium ion efflux to specialized metabolism. Based on the homology, functionally characterized AKRs of all phyla are classified into 16 families and 51 subfamilies (as of September 2021); of which, plant AKRs represent four families (i.e. 2, 4, 6 and 13) and six subfamilies (i.e. 2A, 4A, 4B, 4C, 6C and 13D). Information about the latest nomenclature system as well as the characterized/potential AKRs can be obtained from the AKR database (https://hosting.med.upenn.edu/akr/).

Since the AKR nomenclature committee considered only the functionally characterized AKRs for the classification system and that the biological functions of many plant AKRs are yet to be discovered, the actual phylogeny/diversity realm of plant AKRs remains unknown. To uncover the complete repertoire of AKR gene superfamily in plants, a systematic kingdom-wide identification, phylogeny reconstruction, classification and synteny network clustering analyses were performed using 74 diverse plant genomes and identified 14 AKR subgroups. **To view the subgroup distribution, see AKRsDistributionInPlants.pdf. To view the established phylogeny, see PlantAKRsPhylogeny.svg. To view the synteny networks in Cytoscape or Gephi, see PlantAKRsSyntenyNetwork.cys or PlantAKRsSyntenyNetwork.gephi, respectively.**

# Classification of AKRs via blastp search using RefPlantAKRs dataset
To facilitate the classification of AKRs in a new plant species (i.e. the species not covered in our study), a RefPlantAKRs dataset was prepared with 2044 sequences having 250–550 amino acids in length and only one AKR domain. A pipeline (i.e. PlantAKRsClassification.sh) was then prepared to automate the classification. The pipeline was validated with wheat AKRs (i.e. TaAKRs) as test sample in UBUNTU 18.04.

**Classification proposed here is for gene family characterization studies. If you have any function defined plant AKR, you can check out its subgroup using the materials avialble here. Concurrently, we highly appreciate you to submit the sequence to the AKR superfamily nomenclature committee (https://hosting.med.upenn.edu/akr/existing/) to get a standardized gene symbol.**

# Dependencies
**Seqkit:** To install it, see https://bioinf.shenwei.me/seqkit/download/ or https://anaconda.org/bioconda/seqkit.
**Blast+:** To install it, see https://blast.ncbi.nlm.nih.gov/Blast.cgi?PAGE_TYPE=BlastDocs&DOC_TYPE=Download or https://anaconda.org/bioconda/blast.
**Datamash:** To install it, see https://www.gnu.org/software/datamash/download/ or https://anaconda.org/bioconda/datamash.

# Usage: ./PlantAKRCslassification.sh
**1.** Create a directory and copy your input_ProteinSequence_file (and/or TaAKRs.fa), RefPlantAKRs.fa, and PlantAKRCslassification.sh in the directory.

**2.** First, run the script with TaAKRs.fa (which contains 125 wheat AKRs and 1 non-AKR) available in this repository. After successful execuation, you can run the script with your query sequences. Query sequences (i.e. the ado-keto reductase-domain (PF00248) containing proteins (AKRs) of your target species) can be obtained by locally (e.g. by doing hmmsearch against your target proteome) or by use of any public databases (e.g. https://phytozome-next.jgi.doe.gov/). I prefer the local method (because, we can limit the occurences of non-AKR sequences using gathering threshold option) over the public database (which always includes many non-AKR sequences).

**3.** Make sure that the fasta header of your input_ProteinSequence_file contain only sequence id and no other attributes (for example, see TaAKRs.fa).

**4.** Check line 26 in the PlantAKRsClassification.sh file and input the name of your input_ProteinSequence_file.

**5.** Depending on the seqkit, blast+ and datamash environment, run the script file. If everything is set, just call the script ./PlantAKRsClassification.sh in the terminal. You will get the final output within few seconds (or in a minute, based on your query size) if everything is good. If you use TaAKRs.fa as query, you will see the results within 2 seconds.

**For more details go through the pipeline which includes detailed comments for each and every step.**

# Limitations
The piepline is suitable to classify the AKRs of angiosperms. Classification of AKRs from primitive organisms (e.g. algae) is highly unlikely.

#❗️for any queries reach me at: pselva7@gmail.com
