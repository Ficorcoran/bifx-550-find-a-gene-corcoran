# scripts/

Commands, notebooks, and scripts used in the analysis, plus the analysis log below. 

## Analysis log

| Step | Tool and version or access date | Input | Key parameters | Output | Script |
|---|---|---|---|---|---|
| 2/3 | NCBI tBLASTn, linux, 2026-10-02 | `data/query_human_BDNF_NP_001700.2.fasta` | **database:** Carcharhinus cautus assembly GCA_988281185.1<br>**matrix:** BLOSUM62<br>**E-value threshold:** 1e-5 | `results/blast/tblastn_carcharhinus_cautus_assembly_hits.txt` |`carcharhinus_cautus_genome_tBLASTn_script.txt`|
| 2 | NCBI tBLASTn, web, 2026-10-02 | `data/query_human_BDNF_NP_001700.2.fasta` | **database:** wgs<br>**organism:** Zearaja maugeana (taxid:496415)<br>**matrix:** BLOSUM62<br>**E-value threshold:** 1e-5 | `results/blast/tblastn_wgs_zearaja_maugeana_hits.csv` |Web|
| 4 | NCBI BLASTp, web, 2026-10-02 | `data/novel_carcharhinus_cautus_OZ558480.1-122450059-122450808.faa` | **database:** nr<br>**matrix:** BLOSUM62<br>**E-value threshold:** 1e-5 | `results/blast/blastp_nr_hits_carcharhinus_cautus.csv` |Web|
| 4 | NCBI BLASTp, web, 2026-10-02 | `data/novel_zearaja_maugeana_JCCJZE010001961.1-1890706-1891428.faa` | **database:** nr; **matrix:** BLOSUM62<br>**E-value threshold:** 1e-5 | `results/blast/blastp_nr_hits_zearaja_maugeana.csv` |Web|
| 5 | MAFFT 7.526, linux, 2026-11-06 | `data/bdnf_precursor_unaligned.fasta` | default settings | `results/msa/msa_bdnf_precursor.fasta` | `MAFFT_scripts.txt` |
| 5 | linux, 2026-11-06 | `results/msa/msa_bdnf_precursor.fasta` | N/A | `results/msa/msa_bdnf_mature.fasta` | `trim_mature_BDNF.txt` |
| 5 | MAFFT 7.526, linux, 2026-11-06 | `data/NT_unaligned.fasta` | default settings | `results/msa/msa_NT_aligned.fasta` | `MAFFT_scripts.txt`|
| 6 | [tool, version] | `results/msa/...` | [method; model; bootstrap replicates] | `results/tree/...` |...|
| 7 | [tool, version] | `data/novel_...fasta` | [settings; PDB ID compared] | `results/structure/...` |...|
