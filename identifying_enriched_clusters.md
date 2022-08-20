## Identifying enriched protein clusters
To then identify and annotate enriched protein clusters KinFin version 1.0.3 (Laetsch and Blaxter, 2017) was used in our analysis. KinFin uses as standard input a user specified config file and two output files from OrthoFinder, Orthogroups.txt and SequenceIDs.txt, a functional annotation from InterProScan can be used as well.
Beforehand the InterProScan output has to be converted using `iprs2table.py`which is provided by KinFin at https://kinfin.readme.io/docs/iprs2tablepy.
```
#!/bin/bash

conda activate py27

./kinfin -g Orthogroups_new.txt -c config_new.txt -s SequenceIDs.txt -f 
functional_annotation.txt
```


[functional_annotation.txt.zip](https://github.com/fabib1209/bachelors_thesis_scripts/files/9387097/functional_annotation.txt.zip)
[SequenceIDs.txt.zip](https://github.com/fabib1209/bachelors_thesis_scripts/files/9387102/SequenceIDs.txt.zip)
[config_new.txt](https://github.com/fabib1209/bachelors_thesis_scripts/files/9387093/config_new.txt)
[Orthogroups_new.txt.zip](https://github.com/fabib1209/bachelors_thesis_scripts/files/9387103/Orthogroups_new.txt.zip)



