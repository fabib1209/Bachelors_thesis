## Functional annotation of protein sequences
__Scrips i used for the functional annotation of the protein sequences using InterProScan 5 (Jones et al.,2014).__

Before starting the analysis asterisks had to be removed from nine proteomes.
```
#To remove asterisks from the FASTA files sed was used

#!/bin/bash
sed 's/*//g' input.FASTA > output.FASTA

#All FASTA files were then merged into one big FASTA file

cat *.fa > all_proteins_combined.fa
```
The sequences where then submitted to InteProScan for functional annotation as preparatory work for KinFin analysis. Settings were taken from the KinFin website at https://kinfin.readme.io/docs/starting-from-a-clustering-files.

```
#!/bin/bash -l                                                                              

module purge                                                                

module load openjdk/11.0.2                                                              

export PATH=$PATH:/scratch/fbaltes2/programs/neuneuneu/interproscan-5.56-89.0/

/scratch/fbaltes2/programs/neuneuneu/interproscan-5.56-89.0/interproscan.sh -goterms -appl SignalP-EUK-4.1,Pfam -f TSV -dp -t p -i all_proteomes_combined.faa -b /scratch/fbaltes2/kinfin_all_proteins


