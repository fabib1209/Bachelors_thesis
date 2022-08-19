# Identifying Orthogroups
__In this file, scripts used for identifying the orthogroups using OrthoFinder (Emms and Kelly, 2019) are provided.__

First all proteomes used in the analysis were prepared using the OrthoFinder provided `script primary_transcript.py`.
We had to perform the analysis in two separate steps. The first OrthoFinder run was stopped after calculating the orthogroups. Then the second run was started using the command line option `-fg` to infer gene trees as well as orthologues.

```
#Running Orthofinder v2.5.4 on the primary transcripts
#First run

!/bin/bash 

./orthofinder/OrthoFinder/orthofinder -M msa -T iqtree -t 12 -I 1.5 -a 12 -f /home/jkirangwa/Fabi/primary_transcripts/

#Second run
#Keep going with the option `-fg`

./orthofinder/OrthoFinder/orthofinder -fg /home/jkirangwa/Fabi/primary_transcripts/OrthoFinder/Results_Jul16_6/
```
