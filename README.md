# AcinetobacterPlasmidTyping
AcinetobacterPlasmidTyping comprises a database of _Acinetobacter baumannii_ plasmid replication initiation protein-encoding _rep_ sequences corresponding to an updated plasmid rep typing scheme for _Acinetobacter baumannii_. Rep types are categorised firstly by family (Rep1, Rep3 or RepPriCT; designated R1, R3 and RP respectively in the typing scheme) and secondly type based on homology with a threshold of 95% nucleotide identity. For example, the Rep3 family comprises 69 distinct plasmid _rep_ types (i.e. groups) designated R3-T1 through to R3-T69. Note that multiple _rep_ sequence variants (i.e. allelic variants) can therefore be assigned to the same type/group.  

| Rep Family  | Number of types |Designation |
| ------------- | ------------- |------------- |
| Rep1 (R1) | 6  |R1-T1 to R1-T6  |
| Rep3 (R3) | 69  |R3-T1 to R3-T69  |
| RepPriCT (RP) | 5  |RP-T1 to RP-T5  |

Accessions and isolate metadata for the complete plasmid sequences used to develop the _rep_ typing scheme are available in FigShare via the following DOIs:
- Rep1 family: [10.6084/m9.figshare.20372613](https://dx.doi.org/10.6084/m9.figshare.20372613)
- Rep3 family: [10.6084/m9.figshare.20372598](https://dx.doi.org/10.6084/m9.figshare.20372598)
- RepPriCT family: [10.6084/m9.figshare.20372595](https://dx.doi.org/10.6084/m9.figshare.20372595)

# Usage
Using the AcinetobacterPlasmidTyping database as a reference, users are able to screen their genome assemblies or reads for plasmid _rep_ types with BLAST and SRST2 (https://github.com/katholt/srst2) respectively. 
- To screen genome assemblies, users will need to have BLAST installed before executing the following command:

```[pathway to directory containing blast installation]/bin/blastn -query acinetobacterplasmidtyper.fasta -subject [pathway to directory containing genome assemblies] -outfmt 6 -out results.txt -perc_identity 95```

- To screen reads (use `--input_pe` for paired end and `--input_se` for single end; refer to SRST2 documentation for more information), users will need to have SRST2 installed before executing the following command:

```srst2 --input_pe reads_1.fastq.gz reads_2.fastq.gz --gene_db acinetobacterplasmidtyper.fasta --output results --log```
