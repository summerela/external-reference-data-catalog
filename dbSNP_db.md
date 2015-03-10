##dbSNP
|Description|Format|Lookup|Match_Fields|hg19_download|latest_release|Notes|
|-----------|------|------|------------|---------|---------------|--------------|-----|
|NCBI's dbSNP database|tsv|direct|chrom<br>chromStart<br>chromEnd|[hg19](http://hgdownload.cse.ucsc.edu/goldenPath/hg19/database/snp138Common.txt.gz)|[Recent release](http://hgdownload.cse.ucsc.edu/goldenPath/currentGenomes/Homo_sapiens/database/snp138Common.txt.gz)|<ul><li>Latest download links to most recent human reference</li></ul>|

##dbSNP Database Schema
```Mysql
CREATE TABLE dbSNP_tsv
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
```
						    
