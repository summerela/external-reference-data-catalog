##Cytoband Database
|Description|Format|Lookup|Match_Fields|hg19_download|latest_release|Notes|
|-----------|------|------|------------|---------|---------------|--------------|-----|
|UCSC Cytogenic band database|tsv|direct|chrom<br>chromStart<br>chromEnd|[hg19](http://hgdownload.cse.ucsc.edu/goldenPath/hg19/database/cytoBand.txt.gz)|[Recent release](ftp://hgdownload.cse.ucsc.edu/goldenPath/currentGenomes/Homo_sapiens/database/cytoBand.txt.gz)|<ul><li>Latest download links to most recent human reference</li></ul>|

##Cytoband Database Schema
```Mysql
CREATE TABLE cytoband_db (
chrom         STRING   COMMENT 'Chromosome number','
chromStart    INT      COMMENT 'Start position in genoSeq',
chromEnd      INT      COMMENT End position in genoSeq',
name          STRING   COMMENT 'Name of cytogenetic band',
gieStain      STRING   COMMENT 'Giesma stain results'
)
COMMENT 'cytoBand.txt.gz http://hgdownload.cse.ucsc.edu/goldenPath/hg38/database/cytoBand.txt.gz'
```
