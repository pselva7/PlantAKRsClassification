## 2021-11-02
# Classification of the aldo-keto reductase (AKR) gene superfamily in plants
Aldo-keto reductase-domain (PF00248) containing proteins (AKRs) are NAD(P)(H)-dependent oxidoreductases of a multigene superfamily that mediate versatile functions in plants ranging from detoxification, metal chelation, potassium ion efflux to specialized metabolism. Based on the homology, functionally characterized AKRs of all phyla are classified into 16 families and 51 subfamilies (as of September 2021); of which, plant AKRs represent four families (i.e. 2, 4, 6 and 13) and six subfamilies (i.e. 2A, 4A, 4B, 4C, 6C and 13D). Information about the latest nomenclature system as well as the characterized/potential AKRs can be obtained from the AKR database (https://hosting.med.upenn.edu/akr/).

Since the AKR nomenclature committee considered only the functionally characterized AKRs for the classification system and that the biological functions of many plant AKRs are yet to be discovered, the actual phylogeny/diversity realm of plant AKRs remains unknown. To uncover the complete repertoire of AKR gene superfamily in plants, a systematic kingdom-wide identification, phylogeny reconstruction, classification and synteny network clustering analyses were performed using 74 diverse plant genomes and identified 14 AKR subgroups. **To view the subgroup distribution,** see AKRsDistributionInPlants.pdf. **To view the established phylogeny,** see PlantAKRsPhylogeny.svg. **To view the synteny networks in Cytoscape or Gephi,** see PlantAKRsSyntenyNetwork.cys or PlantAKRsSyntenyNetwork.gephi.

# Classification of AKRs via blastp search using RefPlantAKRs dataset
To facilitate the classification of AKRs in a new plant species (i.e. the species not covered in our study), a RefPlantAKRs dataset was prepared with 2044 sequences having 250–550 amino acids in length and only one AKR domain. Fasta header of the RefPlantAKRs dataset included five attributes (gene id, species, subgroup, protein length and classified criteria) separated by pipe (|). A pipeline (i.e. PlantAKRsClassification.sh) was then prepared to automate the classification. The pipeline was validated with wheat AKRs (i.e. TaAKRs) as test file in UBUNTU 18.04.

**Classification proposed here is for gene family characterization studies. If you have a new plant AKR with defined enzyme activity, you can check out its subgroup using the materials avialble here. Concurrently, we highly appreciate you to submit the sequence to the AKR superfamily nomenclature committee (https://hosting.med.upenn.edu/akr/existing/) to get a standardized gene symbol.**

# Dependencies
**Seqkit:** To install it, see https://bioinf.shenwei.me/seqkit/download/ or https://anaconda.org/bioconda/seqkit.
**Blast+:** To install it, see https://blast.ncbi.nlm.nih.gov/Blast.cgi?PAGE_TYPE=BlastDocs&DOC_TYPE=Download or https://anaconda.org/bioconda/blast.
**Datamash:** To install it, see https://www.gnu.org/software/datamash/download/ or https://anaconda.org/bioconda/datamash.

# Usage
**0.** Download the repostiry. Go to the green background panel **Code** **--> Download ZIP**. The repository will download as PlantAKRsClassification-main.zip. Browse to the downloaded directory and unzip it.

**1.** Create a new directory (lets name it as XYZ).

**2.** Copy **TaAKRs.fa**, **RefPlantAKRs.fa**, and **PlantAKRsClassification.sh** files from the PlantAKRsClassification-main directory into the newly created XYZ directory.

**3.** Open terminal and navigate to the XYZ directory (alternatively you can browse into XYZ and open the terminal there). Once you navigate to the XYZ directory in the terminal, run **chmod +x PlantAKRsClassification.sh** to make the script file as executable (alternatively browse into XYZ --> right click on PlantAKRsClassification.sh --> Properties --> Permissions and tick the Execute: option).

**4.** Depending on the seqkit, blast+ and datamash environment, run the script file using the command **./PlantAKRsClassification.sh** in the terminal. You will get the results within 2 seconds using 10 threads. **Once you get results sucessfully, go to step 5.** Otherwise, make sure whether you run the script in the correct environment, whether the tools are installed successfully and/or whether you export the tool's path to ~/.bashrc.

**5.** Now, you are ready to classify the AKRs of your target plant species. **If you already have query sequences in a file, go to step 6.** Query sequences (i.e. the ado-keto reductase-domain (PF00248) containing proteins (AKRs) of your target species) can be obtained by hmmsearch with hmmer3 tool against your target proteome or by using the keyword PF00248 from any public databases (e.g. https://phytozome-next.jgi.doe.gov/). I prefer the hmmsearch method (because, here, we can limit the occurences of non-AKR sequences using gathering threshold (--cut_ga) option) over the public database search (which always includes many non-AKR sequences). **To install hmmer3** see http://hmmer.org/documentation.html.

**6.** Copy your query sequence file into XYZ. Make sure that the fasta header of your query sequences contain only sequence id and no other attributes (for example, see TaAKRs.fa).

**7.** Check line 26 in the PlantAKRsClassification.sh file and input the name of your query_ProteinSequence_file. Followed by, call the script using the command **./PlantAKRsClassification.sh** in the terminal as described in step 4. You will get the results within few seconds based on your query size.

**For more details, go through the pipeline which includes detailed comments for each and every step.**

# Limitations
The piepline is suitable to classify the AKRs of angiosperms. Classification of AKRs from primitive organisms (e.g. algae) is highly unlikely. And, I have no idea whether the pipeline is usable to classify AKRs from gymnosperms. It is because, the RefPlantAKRs dataset was prepared only using angiosperms.

**#❗️for any queries reach me at: pselva7@gmail.com**
