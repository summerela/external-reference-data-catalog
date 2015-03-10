##RefSeq Gene Definitions
|Description|Format|Lookup|Match_Fields|GRCh37_download|latest_release|Notes|
|-----------|------|------|------------|---------|---------------|--------------|-----|
|RefSeq Gene Definitions|tsv|direct|chrom<br>strand<br>txStart<br>txEnd<br>cdsStart<br>cdsEnd<br>exonCount<br>exonStarts<br>exonEnds|[hg19](http://hgdownload.cse.ucsc.edu/goldenPath/hg19/database/refFlat.txt.gz)|[Recent release](http://hgdownload.cse.ucsc.edu/goldenPath/currentGenomes/Homo_sapiens/database/refFlat.txt.gz)|<ul><li>Latest download links to most recent human reference</li><li>Select match field based on transcript, coding or exon</li></ul>|

##RefSeq Database Schema
```Mysql
CREATE TABLE refseq_genes (
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
   COMMENT 'RefSeq hg19 gene annotations from http://hgdownload.cse.ucsc.edu/goldenPath/hg19/database/refFlat.txt.gz'
						    ```