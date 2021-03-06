Sample queries for ensembl gene annotations for cgi variants
============================================================

Find all variants in ensembl gene regions
-----------------------------------------

The following query can be used to determine what gene regions a variant
lies in and to create a subset for downstream annotation for finding
amino acid changes.

Update or remove the following variables, as needed:  
- cgi.allele1_qual: filter out variants under a specified quality threshold 
- cgi.allele2_qual: filter out alternatitve alleles under a specified quality threshold 
- cgi.totalreadcount: filter out variants that do not have a minimum amount of reads supporting them 
- cgi.zygosity: filter for only entries that are "het-ref" or "hom"

```sql
SELECT cgi.sample_id as cgi_sample_id, cgi.chromosome as cgi_chrom, cgi.start as cgi_start,cgi.stop as cgi_stop,
cgi.reference as cgi_ref,cgi.zygosity as cgi_zygosity,cgi.allele1seq as cgi_alt1, cgi.allele2seq as cgi_alt2, 
cgi.allele1varquality as cgi_alt1qual, cgi.vartype as cgi_vartype,cgi.allele2varquality as cgi_alt2qual,
cgi.totalreadcount as cgi_readcount, ens.start as ensembl_start, ens.stop as ensembl_end, ens.feature, 
ens.gene_name as ensembl_gene_name, ens.gene_id as ensembl_geneid, ens.gene_biotype as ensembl_gene_biotype,
ens.transcript_name as ensembl_tx_name,ens.transcript_id as ensembl_trans_id, ens.exon_id as ensembl_exonid, 
ens.strand as ensembl_strand
FROM p7_ptb.comgen_variant as cgi, public_hg19.ensembl_genes as ens
WHERE cgi.allele1varquality = "VQHIGH"  
AND cgi.totalreadcount > 30
AND cgi.zygosity = "hom"
AND cgi.chromosome = ens.chromosome
AND cgi.start >= ens.start 
AND cgi.stop <= ens.stop
```
Find specific genes in the ensembl gene subset created above
------------------------------------------------------------

Update or remove the following variables, as needed:  
- cgi.allele1_qual: filter out variants under a specified quality threshold 
- cgi.allele2_qual: filter out alternatitve alleles under a specified quality threshold 
- cgi.totalreadcount: filter out variants that do not have a minimum amount of reads supporting them 
- cgi.zygosity: filter for only entries that are "het-ref" or "hom" 
- ens.gene_name: enter comma-separated lsit of accessions number for your genes of interest, with each gene surrounded by quotes

```sql
SELECT cgi.sample_id as cgi_sample_id, cgi.chromosome as cgi_chrom, cgi.start as cgi_start,cgi.stop as cgi_stop,
cgi.reference as cgi_ref,cgi.zygosity as cgi_zygosity,cgi.allele1seq as cgi_alt1, cgi.allele2seq as cgi_alt2, cgi.allele1varquality as cgi_alt1qual, cgi.vartype as cgi_vartype,cgi.allele2varquality as cgi_alt2qual, 
cgi.totalreadcount as cgi_readcount, ens.start as ensembl_start, ens.stop as ensembl_end, ens.feature, ens.gene_name as ensembl_gene_name, ens.gene_id as ensembl_geneid, ens.gene_biotype as ensembl_gene_biotype, ens.transcript_name as ensembl_tx_name,ens.transcript_id as ensembl_trans_id, ens.exon_id as ensembl_exonid, ens.strand as ensembl_strand
FROM p7_ptb.comgen_variant as cgi, public_hg19.ensembl_genes as ens
WHERE cgi.allele1varquality = "VQHIGH"  
AND cgi.totalreadcount > 30
AND cgi.zygosity = "hom"
AND cgi.chromosome = ens.chromosome
AND cgi.start >= ens.start 
AND cgi.stop <= ens.stop
AND ens.gene_name IN ("RP11-523O18.7","RP11-298H24.1", "WDFY4","VSTM4", "LRRC18")
```
Find a specific gene in the ensebml gene subset
-----------------------------------------------

Update or remove the following variables, as needed:  
- cgi.allele1_qual: filter out variants under a specified quality threshold
- cgi.allele2_qual: filter out alternatitve alleles under a specified quality threshold
- cgi.totalreadcount: filter out variants that do not have a minimum amount of reads supporting them 
- cgi.zygosity: filter for only entries that are "het-ref" or "hom" 
- ens.gene_name: enter accession number for your gene of interest surrounded by quotes

```sql
SELECT cgi.sample_id as cgi_sample_id, cgi.chromosome as cgi_chrom, cgi.start as cgi_start,cgi.stop as cgi_stop,
cgi.reference as cgi_ref,cgi.zygosity as cgi_zygosity,cgi.allele1seq as cgi_alt1, cgi.allele2seq as cgi_alt2, cgi.allele1varquality as cgi_alt1qual, cgi.vartype as cgi_vartype,cgi.allele2varquality as cgi_alt2qual, cgi.totalreadcount as cgi_readcount, ens.start as ensembl_start, ens.stop as ensembl_end, ens.feature, ens.gene_name as ensembl_gene_name, ens.gene_id as ensembl_geneid, ens.gene_biotype as ensembl_gene_biotype, ens.transcript_name as ensembl_tx_name, ens.transcript_id as ensembl_trans_id, ens.exon_id as ensembl_exonid, ens.strand as ensembl_strand
FROM p7_ptb.comgen_variant as cgi, public_hg19.ensembl_genes as ens
WHERE cgi.allele1varquality = "VQHIGH"  
AND cgi.totalreadcount > 30
AND cgi.zygosity = "hom"
AND cgi.chromosome = ens.chromosome
AND cgi.start >= ens.start 
AND cgi.stop <= ens.stop
AND ens.gene_name = "VSTM4"
```
Counting features returned
-----------------------------------------------
You can use this format to count features returned, such as zygosity, number of unique gene names, ensemble features.

Update or remove the following variables, as needed:  
- cgi.allele1varquality: filter out variants under a specified quality threshold 
- cgi.allele2varquality: filter out alternatitve alleles under a specified quality threshold 
- cgi.totalreadcount: filter out variants that do not have a minimum amount of reads supporting them 
- cgi.zygosity: filter for only entries that are "het-ref" or "hom" 
- SELECT COUNT(x): replace x with the feature you would like to count
- GROUP BY(X): use the same variable stated in SELECT COUNT(x)

```sql
SELECT COUNT(cgi.vartype)
FROM p7_ptb.comgen_variant as cgi, public_hg19.ensembl_genes as ens
WHERE cgi.allele1varquality = "VQHIGH"  
AND cgi.totalreadcount > 30
AND cgi.chromosome = ens.chromosome
AND cgi.start >= ens.start 
AND cgi.stop <= ens.stop
AND cgi.zygosity = "hom"
GROUP BY cgi.vartype
```
Query to locate intergenic variants
-----------------------------------
Results of this query can be used to locate intergenic variants; downstream analysis can be used to find the two flanking genes, and distances between the variants and the flanking genes.

Update or remove the following variables, as needed:  
- cgi.allele1varquality: filter out variants under a specified quality threshold 
- cgi.allele2varquality: filter out alternatitve alleles under a specified quality threshold 
- cgi.totalreadcount: filter out variants that do not have a minimum amount of reads supporting them 
- cgi.zygosity: filter for only entries that are "het-ref" or "hom"

```sql
SELECT cgi.* 
FROM
p7_ptb.comgen_variant as cgi
LEFT JOIN public_hg19.ensembl_genes as ens
ON cgi.chromosome = ens.chromosome
AND cgi.start >= ens.start 
AND cgi.stop <= ens.stop
WHERE cgi.allele1varquality = "VQHIGH"  
AND cgi.totalreadcount > 30
AND ens.chromosome IS NULL
```
