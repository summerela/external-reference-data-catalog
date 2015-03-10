##UCSC Gene Definitions
|Description|Format|Lookup|Match_Fields|GRCh37_download|latest_release|Notes|
|-----------|------|------|------------|---------|---------------|--------------|-----|
|UCSC Gene Definitions|tsv|direct|chrom,strand,txStart,txEnd,cdsStart,cdsEnd,exonCount,exonStarts,exonEnds|http://hgdownload.cse.ucsc.edu/goldenPath/hg19/database/knownGene.txt.gz|ftp://hgdownload.cse.ucsc.edu/goldenPath/currentGenomes/Homo_sapiens/database/knownGene.txt.gz|*Latest download links to most recent human reference *Select match field based on transcript, coding or exon|

##UCSC Database Schema
```Mysql
CREATE TABLE uniprot_genes (
    name       STRING           COMMENT 'Name of gene',
    chrom      STRING           COMMENT 'Chromosome name',
    strand     STRING           COMMENT '+ or - for strand',
    txStart    INT              COMMENT 'Transcription start position',
    txEnd      INT              COMMENT 'Transcription end position',
    cdsStart   INT              COMMENT 'Coding region start',
    cdsEnd     INT              COMMENT 'Coding region end',
    exonCount  INT              COMMENT 'Number of exons',
    exonStarts INT              COMMENT 'Exon start positions',
    exonEnds   INT              COMMENT 'Exon end positions',
    proteinID  STRING           COMMENT 'UniProtKB ID',
    alignID    STRING           COMMENT 'Unique identifier for each (known gene, alignment position) pair'
    )
COMMENT 'Protein coding genes based on proteins from UniProtKB and their corresponding mRNAs from GenBank downloaded from http://hgdownload.cse.ucsc.edu/goldenPath/hg19/database/knownGene.txt.gz'```
						    
