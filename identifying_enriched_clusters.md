## Identifying enriched protein clusters
To then identify and annotate enriched protein clusters KinFin (Laetsch and Blaxter, 2017) was used in our analysis. KinFin uses as standard input a user specified config file (supplementary) and two output files from OrthoFinder, Orthogroups.txt and SequenceIDs.txt, a functional annotation from InterProScan can be used as well.
Beforehand the InterProScan output has to be converted using `iprs2table.py`which is provided by KinFin at https://kinfin.readme.io/docs/iprs2tablepy.
```
#script provided by KinFin to convert the InterProScan table

#!/bin/bash

/Users/fabi/Desktop/thesis.nosync/kinfin_new/scripts/iprs2table.py -i kinfin_all_proteins.tsv


