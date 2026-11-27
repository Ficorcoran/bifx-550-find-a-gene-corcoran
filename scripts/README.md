# scripts/

Commands, notebooks, and scripts used in the analysis, plus the analysis log below. 

## Analysis log, C. Cautus

| Step | Candidate Species | Tool and version or access date | Input | Key parameters | Output | Script |
|---|---|---|---|---|---|---|
| 2/3 | *C. cautus* | NCBI tBLASTn, EMBOSS transeq, 2026-10-02 | `data/query_human_BDNF_NP_001700.2.fasta` | **database:** Carcharhinus cautus assembly GCA_988281185.1<br>**matrix:** BLOSUM62<br>**E-value threshold:** 1e-5 | `results/blast/tblastn_carcharhinus_cautus_assembly_hits.txt` |`carcharhinus_cautus_genome_tBLASTn_script.txt`|
| 2 | *Z. maugeana* | NCBI tBLASTn, web, 2026-10-02 | `data/query_human_BDNF_NP_001700.2.fasta` | **database:** wgs<br>**organism:** Zearaja maugeana (taxid:496415)<br>**matrix:** BLOSUM62<br>**E-value threshold:** 1e-5 | `results/blast/tblastn_wgs_zearaja_maugeana_hits.csv` |N/A|
| 3 | *Z. maugeana* | EMBOSS transeq, 2026-10-02 | `data/novel_zearaja_maugeana_JCCJZE010001961.1-1890706-1891428_nuc.faa`| N/A | `data/novel_zearaja_maugeana_JCCJZE010001961.1-1890706-1891428.faa` | `translate_ORF.txt`|
| 4 | *C. cautus* | NCBI BLASTp, web, 2026-10-02 | `data/novel_carcharhinus_cautus_OZ558480.1-122450059-122450808.faa` | **database:** nr<br>**matrix:** BLOSUM62<br>**E-value threshold:** 1e-5 | `results/blast/blastp_nr_hits_carcharhinus_cautus.csv` |N/A|
| 4 | *Z. maugeana* | NCBI BLASTp, web, 2026-10-02 | `data/novel_zearaja_maugeana_JCCJZE010001961.1-1890706-1891428.faa` | **database:** nr; **matrix:** BLOSUM62<br>**E-value threshold:** 1e-5 | `results/blast/blastp_nr_hits_zearaja_maugeana.csv` |N/A|
| 5 | Both | MAFFT 7.526, linux, 2026-11-06 | `data/bdnf_precursor_unaligned.fasta` | default settings | `results/msa/msa_bdnf_precursor.fasta` | `MAFFT_scripts.txt` |
| 5 | Both | linux, 2026-11-06 | `results/msa/msa_bdnf_precursor.fasta` | N/A | `results/msa/msa_bdnf_mature.fasta` | `trim_mature_BDNF.txt` |
| 5 | Both | MAFFT 7.526, linux, 2026-11-06 | `data/NT_unaligned.fasta` | default settings | `results/msa/msa_NT_aligned.fasta` | `MAFFT_scripts.txt`|
| 6 | Both | MEGA12, JTT, 11-06-26 | `results/msa/msa_bdnf_precursor.fasta` | **method:** Maximum Likelihood<br> **model:** JTT+G+I<br>**bootstrap replicates:** 500 | `results/tree/msa_bdnf_precursor_tree.nwk` |N/A|
| 6 | Both | MEGA12, JTT, 11-06-26 | `results/msa/msa_bdnf_mature.fasta` | **method:** Maximum Likelihood<br> **model:** JTT+G<br>**bootstrap replicates:** 500 | `results/tree/msa_bdnf_mature_tree.nwk` |N/A|
| 6 | Both | MEGA12, JTT, 11-06-26 | `results/msa/msa_NT_aligned.fasta` | **method:** Maximum Likelihood<br> **model:** JTT+G<br>**bootstrap replicates:** 500 | `results/tree/msa_NT_aligned_tree.nwk` |N/A|
| 7 | *C. cautus* | ColabFold with AlphaFold2-Mulitmer V3, 11-22-26; PyMOL Version 3.1.0 | `data/bdnf_mature_shark.fasta` | default ColabFold settings; 1BND for comparison | `results/structure/shark_28d8e_unrelaxed_rank_001_alphafold2_multimer_v3_model_1_seed_000.pdb` |N/A|
| 7 | *Z. maugeana* | ColabFold with AlphaFold2-Mulitmer V3, 11-22-26; PyMOL Version 3.1.0 | `data/bdnf_mature_skate.fasta` | default ColabFold settings; 1BND for comparison | `results/structure/skate_bc9fc_unrelaxed_rank_001_alphafold2_multimer_v3_model_1_seed_000.pdb` |N/A|

