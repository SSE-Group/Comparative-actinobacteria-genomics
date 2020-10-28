# Comparative actinobacteria genomics
Code reository for the paper titled `Comparative genomics reveals sanitary and catabolic capabilities of Actinobacteria within the fungus-farming termite symbiosis`


Contact:
	Rob Murphy
	robert.murphy@bio.ku.dk


-------> indicated the batch script submits the call script on a slurm job queue system on a HPC with conda environment manager.


## BGC antiSMASh analysis
	
	`antismash-batch.sh` ------> antismash-call.sh (runs antismash)
	Use the APP.py script for an all in one analysis (seperate scripts can be provided for each step).

	stats analysis:
		antismash_stats_analysis.R

## Hotpepe CAZYme analysis
	
	Hotpep was run locally on a windows machine
	Use the following scripts in the order given

		hotpep_EC_scrape.R (isolates and cleans up the EC numbers given by hotpep)
		EC_to_name.py (provides an enzyme name for a given EC number through searching the expasys database)
		summarise_hotpep.py

	stats analysis:
		hotpep_stats_analysis.R

## MLST phylogenetic analysis
	
	Use the following scrips in the order given:
		busco-bash.sh ------> busco-call.sh (isolates genes to use for MLST)
		compile_busco.py (compiles genes identified by busco to a user defined lineage where said genes is present in 3 or more isolates)
		clustalo-batch.sh ------> clustalo-call.sh (alignes all genes)
		raxml-ng-batch.sh ------> raxml-ng-call.sh (generated gene trees)
		astralPro-call.sh (concatinated gene trees)
