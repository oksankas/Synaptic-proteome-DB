# Synaptic-proteome-DB
The tables and R code to populate Synaptic Proteome SQLite DB

	
 
![image](https://user-images.githubusercontent.com/1798733/113897717-0e580b00-97c3-11eb-860d-704b905ba685.png)


The database contains the following main tables: 
-	Gene: list of genes including IDs (MGI, Entrez Human and Mouse) and gene names (Human and Mouse).
-	Specie: Tax ID (Human and Mouse)
-	Paper: list of papers with PMID ID, name (in format “FirstAuthor_year”), year of publication
-	Location: postsynaptic, presynaptic, synaptosome
-	Method: shotgun or IP
-	Brain region: list of regions where the samples originate, with hierarchical region structure
-	PPI: human protein-protein interactions combined from BioGRID, Intact and DIP databases, contain information on methods, interaction type (PSI-MI nomenclature) and PMID info for each of the interactions.
-	PaperGene: table links gene to respective papers and the metadata above
-	GO: BP, CC and MF GO annotation for Human, Mouse and Rat species
-	GOGene: gene to GO association list
-	Disease: List of diseases from HDO for Human
-	DiseaseGene: genes to disease association list
-	GeneToModel: genes with found association with published model of synaptic plasticity
The database is created with SQLite v 3.31.1 RDBMS in SQLite Studio v3.2.1. 
The database is easily accessible from SQLite Studio (the separate manual and screencast provided). The database is accessible from RStudio (Rmd provided, you just need specify the path to the database).

All the table that combined in the database and R code that makes an sqlite from them are available from GitHub (ref). The easiest way to integrate the own dataset would be:
 1) select appropriate localisation table from Presynaptic (“Pres_DB_April21.txt”), Postsynaptic (“PSD_db_Oct20.txt”), or Synaptosome (“Syn_DB_April21.txt”) and add a new column in a way similar to previously collected studies.
 2) Edit table “Full_DB_April21” with the new genes, if any. 
3) Edit the table Paper_Summary_April21” to add new study, if any 
4) Run the R code Populate_DB_April21 to rebuild the database from scratch. Make sure you provide right paths to the tables.

