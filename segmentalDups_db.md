##Segmental Duplications
|Description|Format|Lookup|Match_Fields|hg19_download|latest_release|Notes|
|-----------|------|------|------------|---------|---------------|--------------|-----|
|UCSC's segmental duplication databsae|tsv|direct|chrom<br>chromStart<br>chromEnd|[hg19](http://hgdownload.cse.ucsc.edu/goldenPath/hg19/database/genomicSuperDups.txt.gz)|[Recent release](http://hgdownload.cse.ucsc.edu/goldenPath/currentGenomes/Homo_sapiens/database/genomicSuperDups.txt.gz)|<ul><li>Latest download links to most recent human reference</li></ul>|

##dbSNP Database Schema
```Mysql
CREATE TABLE genomicSuperDups
(
chrom       STRING  COMMENT 'Chromosome or FPC contig',
chromStart  INT     COMMENT 'Start position in chromosome',
chromEnd    INT     COMMENT 'End position in chromosome',
name        STRING  COMMENT 'Other chromosome involved',
score;      INT     COMMENT 'Score from 900-1000.  1000 is best',
strand      STRING  COMMENT 'Value should be + or -',
otherChrom  STRING  COMMENT 'Other chromosome or FPC contig',
otherStart  INT     COMMENT 'Start in other  sequence',
otherEnd    INT     COMMENT 'End in other  sequence',
otherSize   INT     COMMENT 'Total size of other sequence',
uid         INT     COMMENT 'Unique ID',
posBasesHit INT     COMMENT 'HitPositive UnCovered',
testResult  STRING  COMMENT 'HitPositive (yes or no) UnCovered (covered=0)',
verdict     STRING  COMMENT 'Real or Allele',
alignfile   STRING  COMMENT 'Alignment file path',
alignL      INT     COMMENt 'Spaces/positions in alignment',
indelN      INT     COMMENT 'Number of indels',
indelS      INT     COMMENT 'Indel spaces',
alignB      INT     COMMENT 'Bases Aligned',
matchB      INT     COMMENT 'Aligned bases that match',
mismatchB   INT     COMMENT 'Aligned bases that do not match',
transitionsB INT    COMMENt 'Number of transitions',
transversionsB INT  COMMENT 'Number of transversions',
fracMatch    FLOAT  COMMENT 'Fraction of matching bases',
fracMatchIndel FLOAT COMMENT 'Fraction of matching bases with indels',
jcK         FLOAT   COMMENT 'K-value calculated with Jukes-Cantor',
k2K         FLOAT   COMMENT 'Kimura K'
)
COMMENT 'Summary of large genomic Duplications (>1KB >90% similar) from http://hgdownload.cse.ucsc.edu/goldenPath/hg38/database/genomicSuperDups.txt.gz'
```
						    
