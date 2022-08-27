# Predicting enzyme functions
__To predict enzyme commission (EC) numbers for query IDs in every proteome, DeepEC version 0.4.0 (Ryu et al. 2019) was used.__

```
#Script for using DeepEC on every proteome

#!/bin/bash

for file in *.fa
  
do
	name="${file%.*}"
  	 file_output="${name}" #Because DeepEC names every file the same, we added this to specifically name every output file
python deepec.py -i $file -o /Users/fabi/Desktop/thesis.nosync/results_deepec/${file_output}/
done
```

Duplicates were removed and the files sorted with `sort -u`.

Shared EC numbers between free-living and parasitic species were searched using `comm`.

```
#grouping the EC numbers according to habitat of the species

#shared between parasites and free-living
comm -12 sorted_EC_para.txt sorted_EC_free.txt > shared_between_pf.txt

#Only present in parasites
comm -13 shared_between_pf.txt sorted_EC_para.txt > parasites_EC.txt

#Only present in free-living
comm -13 shared_between_pf.txt sorted_EC_free.txt > freeliving_EC.txt
```
## Searching sequences for KEGG annotation

As input for ghoastKOALA, protein sequences are needed, therefore the EC numbers of the ‘shared’ groups were reconnected to their query ID.

```
#First the corresponding genenames for the EC numbers were searched

 while read line
do
        echo $line
        grep "\<${line}\>" all_EC.txt  >> shared_between_genenames.txt
done < shared_between_pf.txt


Then query IDs and sequences were reconnected from a file with all proteomes merged.

```
#!/bin/bash
seqtk subseq 36_combined.fa shared_between_genenames.txt > sequences_shared_pf.fa


These sequences were then submitted to GhostKOALA.







