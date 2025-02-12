# AcinetobacterPlasmidTyping
AcinetobacterPlasmidTyping comprises a database of _Acinetobacter_ plasmid replication initiation protein-encoding _rep_ sequences corresponding to an updated plasmid rep typing scheme for _Acinetobacter baumannii_. Rep types are categorised firstly by family (Rep1, Rep3 or RepPriCT; designated R1, R3 and RP respectively in the typing scheme) and secondly by type based on homology with a threshold of 95% nucleotide identity. For example, the Rep3 family comprises 78 distinct plasmid _rep_ types (i.e. groups) designated R3-T1 through to R3-T79. Note that multiple _rep_ sequence variants (i.e. allelic variants) can be assigned to the same type/group.  

| Rep Family  | Number of types |Designation |
| ------------- | ------------- |------------- |
| Rep1 (R1) | 25  |R1-T1 to R1-T26  |
| Rep3 (R3) | 200  |R3-T1 to R3-T201  |
| RepPriCT_1 (RP) | 32  |RP-T1 to RP-T32  |


# Database Version Updates
VERSION 3.0 (February 2025)
- complete plasmids from all Acinetobacter species publically available (as of March 23, 2023) are included. The APT database now includes 257 rep sequence types
- Metadata, antibiotic resistance genes and rep sequence types of 1848 complete Acinetobacter plasmids are available at https://figshare.com/account/projects/230963/articles/28003661?file=51090473

Rep Type	Reference plasmid in Rep multi-FASTA database	Plasmid Accession	Species
R1-T1	pMRSN58-2.7	CM003316.1	A. baumannii
R1-T2	pAB49	L77992.1	A. baumannii
R1-T4	p3AB5075	CP008709.1	A. baumannii
R1-T5	pTS236	JN872565.1	A. baumannii
R1-T6	pMRSN56-1	CP080453.1	A. baumannii
R1-T7	pDETABR21-4	CP088899.1	A. baumannii
R1-T8	pOCUAc18-9	AP024811.1	A. baumannii
R1-T9	pM131-9	NC_025118.1	Acinetobacter sp.
R1-T10	p6AB105	NZ_CP103343.1	A. baumannii
R1-T11	pM131-10	NC_025169.1	Acinetobacter sp.
R1-T12	p12	NZ_CP033121.1	A. wuhouensis
R1-T13	pAhaem11616b	NZ_CP032007.1	A. haemolyticus
R1-T14	p8_060092	NZ_CP035943.1	A. cumulans
R1-T15	p4FDAARGOS_731	NZ_CP059689.1	A. radioresistens
R1-T16	pC9_7	NZ_CP113449.1	A. baumannii
R1-T17	pC9_7	NZ_CP113449.1	A. baumannii
R1-T18	pAhaemAN3a	NZ_CP031987.1	A. haemolyticus
R1-T19	pIC001D	NZ_CP022302.1	A. johnsonii
R1-T20	p2	NZ_CP041367.1	A. tandoii
R1-T21	p94-2-p5	NZ_CP041289.1	A. indicus
R1-T22	pXMC5X702-2.3k	NZ_CP084311.1	A. pseudolwoffii
R1-T23	p2021CK-01005-7	NZ_CP104658.1	A. variabilis
R1-T24	pXM9F202-2-2k	NZ_CP060816.1	A. variabilis
R1-T25	pYUSHP14-6	NZ_CP090073.1	Acinetobacter sp.
R1-T26	pNY13623-3	NZ_CP106991.1	A. baumannii
![image](https://github.com/user-attachments/assets/287e506a-a9ed-42a1-b6ba-ed789f2abbfa)







VERSION 2.0 (September 2023)
- R1-T3 has been retired due to sequencing/assembly error  
- R3-T49 has been retired (the sequence originally named R3-T49 has been re-named R3-T26*)



# Accessions and isolate metadata for the complete plasmid sequences used to develop the _rep_ typing scheme are available in FigShare via the following DOIs:

- Rep1 family: [10.6084/m9.figshare.20372613](https://dx.doi.org/10.6084/m9.figshare.20372613) (December 2022)
- Rep3 family: [10.6084/m9.figshare.20372598](https://dx.doi.org/10.6084/m9.figshare.20372598) (December 2022)
- RepPriCT_1 family: [10.6084/m9.figshare.20372595](https://dx.doi.org/10.6084/m9.figshare.20372595) (December 2022)

- Summary of strains carrying plasmids, their metadata, and AMR genes carried by their plasmids: https://doi.org/10.6084/m9.figshare.24076776 (September 2023)
- Summary of complete plasmids, their Rep types, metadata and antibiotic resistance gene: https://doi.org/10.6084/m9.figshare.24076779 (September 2023) 


# Usage
Using the AcinetobacterPlasmidTyping database as a reference, users are able to screen their genome assemblies or reads for plasmid _rep_ types with BLAST and SRST2 (https://github.com/katholt/srst2) respectively. 
- To screen genome assemblies, users will need to have BLAST installed before executing the following command:

```[pathway to directory containing blast installation]/bin/blastn -query acinetobacterplasmidtyper.fasta -subject [pathway to directory containing genome assemblies] -outfmt 6 -out results.txt -perc_identity 95```

- To screen reads (use `--input_pe` for paired end and `--input_se` for single end; refer to SRST2 documentation for more information), users will need to have SRST2 installed before executing the following command:

```srst2 --input_pe reads_1.fastq.gz reads_2.fastq.gz --gene_db acinetobacterplasmidtyper.fasta --output results --log```

# References
1) Lam MMC, Koong J, Holt KE, Hall RM, Hamidian M. Detection and Typing of Plasmids in _Acinetobacter_ _baumannii_ Using _rep_ Genes Encoding Replication Initiation Proteins. Microbiol Spectr. 2023 Feb 14;11(1):e0247822. doi: 10.1128/spectrum.02478-22. PMID: 36472426; PMCID: PMC9927589. https://pubmed.ncbi.nlm.nih.gov/36472426/
2) Lam MMC, Hamidian M. Examining the role of _Acinetobacter_ _baumannii_ plasmid types in disseminating antimicrobial resistance. npj Antimicrob Resist 2, 1 (2024). https://doi.org/10.1038/s44259-023-00019-y
