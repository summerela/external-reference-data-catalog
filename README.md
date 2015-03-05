# external reference data catalog

a collection of information about the various external data types we work with

The purpose of this repository is to document the various external bioinformatics data sources, data types, and databases that we work with.  We will try to add documentation on the external source, a short description, as well as example SQL-style schema which reflects our current usage(s) of this data here in the lab.

## Kaviar
## ClinVar
## Gene annotations
these are currently coming from ITMI's local version of Refseq and UCSC. We could possibly use ensembl tsv files for this, but if anyone has a better solution already in place, please do let us know

## Cytoband
## RepeatMasker
## Segmental Duplications
## dbSNP

### original format: tsv
### current source: https://s3.amazonaws.com/itmi.ptb.datafreeze/annotation/dbsnp138_cgfv5_filt.tsv.gz	
### fields to match on
```chrom
chromStart
chromEnd
```
### database schema
* source: http://genome.ucsc.edu/cgi-bin/hgTables?db=hg19&hgta_group=varRep&hgta_track=snp137Common&hgta_table=snp137Common&hgta_doSchema

* db definition
```
"CREATE TABLE dbSNP_tsv
   (
   bin               INT       COMMENT 'UCSC bin scheme for db optimization',
   chrom             STRING    COMMENT 'Chromosome identifier for the genome',
   chromStart        INT       COMMENT 'Start position, 0 based',
   chromEnd          INT       COMMENT 'End position',
   name              STRING    COMMENT 'rsID',
   score             INT,     
   strand            ENUM('+', '-'),      
   refNCBI           STRING,   
   refUCSC           STRING,
   observed          STRING,
   molType           STRING,
   class             STRING,
   valid             STRING,
   avHet             INT        COMMENT 'Avg heterozygosity',
   avHetSE          INT,
   func              STRING     COMMENT 'Functional effect of variant on RefSeq transcripts',
   locType           STRING,     
   weight            INT        COMMENT 'Alignment quality 1 = best',
   exceptions        STRING     COMMENT 'Exceptions implying SNP not properly mapped',
   submitterCount    INT        COMMENT 'Number of submitters',
   submitters        STRING     COMMENT 'Consortia handle of submitter',
   alleleFreqCount   INT,
   alleles           STRING,
   alleleNs          STRING,
   alleleFreqs       INT,
   bitfields         STRING     COMMENT 'SNP validation'
   )
COMMENT 'dbSNP snp138Common.txt.gz, hg19 flat file from  http://hgdownload.cse.ucsc.edu/goldenPath/hg19/database/snp138Common.txt.gz'
"
```
### Latest version
http://hgdownload.cse.ucsc.edu/goldenPath/hg19/database/snp138Common.txt.gz

## Admix4
## Admix14
## PolyPhen/SIFT
## miRNA
## UW ESP
## PFAM
