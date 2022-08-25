## Linking protein domains to KEGG pathways

First the genes from the enriched protein domains from KinFin output were searched in the OrthoFinder output Orthogroups.tsv.
Via `grep` the enriched clusters were searched.
The genes from the enriched parasitic clusters were filtert out and the analysis was continued only with parasitic species.
These genes were matched with EC numbers, via `grep`, from DeepEC (all_EC.txt) to filter out genes without annotation.

Genes with an EC number were than matched with their respective KEGG annotation.
```
  while read line
do
        echo $line
        grep "\<${line}\>" results_detail_sharedpf_KEGG.txt >> enriched_pathways.txt
done < enriched_genenames.txt

From 'enriched_pathways' the K numbers were sorted out and the KEGG-pathways tool (https://www.kegg.jp/kegg/pathway.html) used to search for the pathways the K numbers are active in.
´´´
















[enriched_pathways.txt](https://github.com/fabib1209/Bachelors_thesis/files/9424884/enriched_pathways.txt)
[results_detail_sharedpf_KEGG.txt](https://github.com/fabib1209/Bachelors_thesis/files/9424865/results_detail_sharedpf_KEGG.txt)
[enriched_genenames.txt](https://github.com/fabib1209/Bachelors_thesis/files/9424881/enriched_genenames.txt)
[Orthogroups.tsv.zip](https://github.com/fabib1209/Bachelors_thesis/files/9424809/Orthogroups.tsv.zip)
[all_EC.txt](https://github.com/fabib1209/Bachelors_thesis/files/9424834/all_EC.txt)
