# BDNF: Find-a-Gene analysis in Carcharhinus Cautus

BIFX-550 Computational Functional Genomics, Hood College, Fall 2026
Author: Fiona Corcoran (ficorcoran)

## Summary

This project aimed to identify the gene Brain Derived Neurotrophic Factor (BDNF) in a species which it had not been described, using *Homo sapiens* as a reference. Two species were used, *Carcharhinus cautus* (Nervous Shark) and *Zearaja maugeana* (Maugean Skate). Candidate sequences were identified using tBLASTn, then confirmed as novel with BLASTp against the nr database. Phylogenetic trees of the full sequence and mature sequence of BDNF were constructed using MAFFT alignment and MEGA12 tree modeling. A third tree was made with multiple neurotrophin family proteins to confirm the identified sequences as BDNF. Finally, ColabFold with AlphaFold2 Multimer v3 was used to predict the structure of both sequences as homodimers, and then compared to the existing computationally determined human BDNF structure, PDB 1BND. 

This project was used to apply skills relating to sequence alignments, MSA, phylogenetic tree construction, and modeling prediction as part of the Hood College BIFX550 Functional Genomics course, Fall 2026.


| Item | Value |
|---|---|
| Starting protein | Brain Derived Neurotrophic Factor (BDNF) |
| Starting species | *Homo Sapiens* |
| Starting accession | NP_001700.2 |
| Novel candidate | Hypothetical *C. cautus* BDNF, Hypothetical *Z. maugeana* BDNF |
| Source organism | *Carcharhinus cautus*, *Zearaja maugeana* |
| Source nucleotide record | GCA_988281185.1 (*C. cautus*), scaffold 17, JCCJZE010001961.1:1890706–1891428 (*Z. maugeana*) |
| Novelty evidence, *C. cautus* | BLASTp top hit in nr: *Carcharhinus amblyrhynchos*, XP_080047658.1, score: 514, E-value 0.0, % Identity 100.00% |
| Novelty evidence, *Z. maugeana* | BLASTp top hit in nr: *Raja brachyura*, XP_080095090.1, score: 502, E-value 3e-179, % Identity 99.59% |
| Structure prediction | ColabFold with AlphaFold2 Multimer V3, mean pLDDT 88.18 (*C. cautus*), 88.62 (*Z. maugeana*) |
| Closest PDB entry | PDB 1BND |

## Repository structure

```
.
├── README.md           project summary (this file)
├── data/               sequences in FASTA format
├── scripts/            commands, notebooks, and the analysis log
├── results/
│   ├── blast/          tBLASTn and BLASTp output
│   ├── msa/            multiple sequence alignment
│   ├── tree/           phylogenetic tree files and images
│   └── structure/      predicted models, images, PDB comparison
└── report/             bifx550c written report (Word)
```

## Workflow

| Step | Task | Tool | Output |
|---|---|---|---|
| 1 | Choose a starting protein | UniProt or NCBI Protein | `data/` |
| 2 | Search for a candidate novel gene | tBLASTn against WGS or whole genome for *C. cautus* | `results/blast/` |
| 3 | Retrieve and translate the ORF | GenBank record, ORF translation using EMBOSS transeq | `data/` |
| 4 | Confirm novelty | BLASTp against nr | `results/blast/` |
| 5 | Multiple sequence alignment | MAFFT | `results/msa/` |
| 6 | Phylogenetic tree | MEGA12; maximum likelihood, JTT+G+I | `results/tree/` |
| 7 | Structure prediction and comparison | ColabFold with ALphaFold2 Multimer v3; PyMOL | `results/structure/` |
| 8 | Discussion | | `report/` |

Tool versions, access dates, and parameters for every step are recorded in [scripts/README.md](scripts/README.md).

## Key results

### Novelty
Both BLASTp searches resulted in very high percentage identity matches in similar species, the grey reef shark for the nervous shark, and the blonde ray for the maugean skate. However, there were no matches in the nr database for either of the candidate species, indicating that the identification of BDNF in these species is novel.

### Alignment and phylogeny
Three maximum likelihood phylogenetic trees were constructed using MEGA12 maximum likelihood with 500 bootstrap replicates: full-length BDNF, mature BDNF, and the broader neurotrophin family. The full-length tree generally produced expected evolutionary relationships, with cartilaginous fishes forming a strongly supported clade (100% bootstrap support). The nervous shark grouped with other sharks (80% support), while the Maugean skate clustered with other skates (100% support). The mature BDNF tree showed similar relationships but generally lower bootstrap support, likely due to the high conservation of the mature protein. The neurotrophin family tree grouped the candidate sequences with known BDNF proteins rather than other neurotrophins, providing additional evidence that both sequences are BDNF orthologs.

### Structure
Both candidate BDNF proteins were modeled as homodimers using ColabFold with AlphaFold2-Multimer v3. The nervous shark and maugean skate had mean pLDDT values of 88.18 and 88.62, respectively, indicating relatively high confidence in both predicted structures. Both models also had pTM scores of 0.84 and ipTM scores of 0.82. The structures were then aligned with experimentally determined human BDNF (PDB 1BND) using PyMOL, producing refined RMSDs of 0.453 Å for the shark and 0.463 Å for the skate. Both models showed small terminal extensions that were absent from the human structure, although these appear to be due to unresolved residues in the experimental structure rather than actual differences in the proteins. Overall, the close structural similarity between all three species further demonstrates how well conserved mature BDNF is across vertebrates.

## Limitations and next steps

There were several limitations to this analysis. Many of the comparison sequences used in the multiple sequence alignment were computationally predicted RefSeq proteins, and some precursor regions contained low-complexity sequences that were difficult to align reliably. Along with this, the experimental structure used for comparison (PDB 1BND) also had some geometric outliers in its wwPDB validation report and was determined as a heterodimer with NT3 rather than a BDNF homodimer.  Additionally, structural predictions and sequence similarity cannot independently establish the biological activity of the identified proteins.

A possible future direction would be to investigate the distribution of this region across additional species to help determine when it arose and whether it has any functional significance, although this may be difficult due to its low complexity. Another related direction would be to investigate the possible evolutionary pressure differences between the mature region and the propeptide region, given the clear difference in conservation.

## Reproducing this analysis

Inputs are in `data/`. Every step, with its tool, version or access date, parameters, input, and output, is listed in the analysis log in [scripts/README.md](scripts/README.md). Following that log in order reproduces the results in `results/`.

## Use of AI tools

ChatGPT (OpenAI) was used to clarify bioinformatics concepts and tools, assist with identifying appropriate computational methods and provide feedback on grammar, wording, and organization. Scientific claims and references were verified using cited primary sources, and the final report and repository were written and revised by the author.

## References

[Databases, tools, and papers used, with versions or access dates. Include the course template: BIFX-550 Find-a-Gene template, github.com/ravichas/bifx550-find-a-gene-template.]
