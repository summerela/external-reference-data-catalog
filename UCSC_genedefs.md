##UCSC Gene Definitions
Protein coding genes based on proteins from UniProtKB and their corresponding mRNAs from GenBank

|Match_On| Downloads|Sample_Query|Notes|
|------------|---------|--------------|------------|-----|
|chrom<br>strand<br>txStart<br>txEnd<br>cdsStart<br>cdsEnd<br>exonCount<br>exonStarts<br>exonEnds|[hg19](http://hgdownload.cse.ucsc.edu/goldenPath/hg19/database/knownGene.txt.gz)<br>[Recent release](http://hgdownload.cse.ucsc.edu/goldenPath/currentGenomes/Homo_sapiens/database/knownGene.txt.gz)|tbd|[Documentation](http://genome.ucsc.edu/cgi-bin/hgTables)<br><br>Latest download links to most recent human reference. |

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
COMMENT 'Protein coding genes based on proteins from UniProtKB and their corresponding mRNAs from GenBank downloaded from http://hgdownload.cse.ucsc.edu/goldenPath/hg19/database/knownGene.txt.gz'
```
						    
