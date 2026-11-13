# BDNF: Find-a-Gene analysis in Carcharhinus Cautus

] **Template:** replace every item in angle brackets `[ ]`, then delete this line. See [GETTING_STARTED.md](GETTING_STARTED.md) for how to add files.

BIFX-550 Computational Functional Genomics, Hood College, Fall 2026
Author: Fiona Corcoran (ficorcoran)

## Summary

This project aimed to identify the gene Brain Derived Neurotrophic Factor (BDNF) in a species which it had not been described, using homo sapiens as a reference. A shark which had recently had its genome sequenced--Carcharhinus cautus (Nervous Shark)--was identified as a candidate. As the shark had a whole genome sequence GCA_988281185.1, but had not yet been added to the BLAST database, the genome was downloaded as a FASTA file and tblastn was run locally, finding a strong match. This candidate was then confirmed with reciprocal best hit and analyzing the function of the sequences with the greatest amount of changes.


| Item | Value |
|---|---|
| Starting protein | Brain Derived Neurotrophic Factor (BDNF) |
| Starting species | Homo Sapiens |
| Starting accession | NP_001700.2 |
| Novel candidate | [Name, or "hypothetical protein" / "unnamed"] |
| Source organism | Carcharhinus cautus |
| Source nucleotide record | GCA_988281185.1 |
| Novelty evidence | [BLASTp top hit in nr: annotation, % identity, E-value] |
| Structure prediction | [Tool; mean pLDDT or QMEAN] |
| Closest PDB entry | [PDB ID] |

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
| 2 | Search for a candidate novel gene | tBLASTn against WGS or TSA | `results/blast/` |
| 3 | Retrieve and translate the ORF | GenBank record, ORF translation | `data/` |
| 4 | Confirm novelty | BLASTp against nr | `results/blast/` |
| 5 | Multiple sequence alignment | MAFFT | `results/msa/` |
| 6 | Phylogenetic tree | MEGA; maximum likelihood, JTT | `results/tree/` |
| 7 | Structure prediction and comparison | [AlphaFold, ColabFold, or SWISS-MODEL; Mol* or ChimeraX] | `results/structure/` |
| 8 | Selection analysis (optional) | [HyPhy or PAML] | `results/selection/` |
| 9 | Discussion | | `report/` |

Tool versions, access dates, and parameters for every step are recorded in [scripts/README.md](scripts/README.md).

## Key results

### Novelty
[What the BLASTp search against nr returned and why the candidate counts as novel.]

### Alignment and phylogeny
[Conserved regions; where the novel protein falls in the tree; support values.]

### Structure
[Prediction confidence; similarity to the closest PDB entry; notable differences.]

## Limitations and next steps

[What the evidence cannot show, and what you would test next.]

## Reproducing this analysis

Inputs are in `data/`. Every step, with its tool, version or access date, parameters, input, and output, is listed in the analysis log in [scripts/README.md](scripts/README.md). Following that log in order reproduces the results in `results/`.

## Use of AI tools

[Name any AI tool that contributed materially and describe how, or write "None."]

## References

[Databases, tools, and papers used, with versions or access dates. Include the course template: BIFX-550 Find-a-Gene template, github.com/ravichas/bifx550-find-a-gene-template.]
