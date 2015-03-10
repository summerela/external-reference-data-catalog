##Ensembl Gene Definitions
|Description|Format|Lookup|Match_Fields|GRCh37_download|latest_release|Notes|
|-----------|------|------|------------|---------|---------------|--------------|-----|
|Ensembl Gene Definitions|tsv|direct|seqname<br>start<br>end|[hg19](http://ftp.ensembl.org/pub/release-74/gtf/homo_sapiens/Homo_sapiens.GRCh37.74.gtf.gz)|[Recent release](http://ftp.ensembl.org/pub/current_gtf/homo_sapiens/Homo_sapiens.GRCh38.78.gtf.gz)|<ul><li>Latest download links to most recent human reference</li><li>We might want to break up the "attribute" field into separate columns</li></ul>|

##Ensembl Database Schema
```Mysql
CREATE TABLE ensembl_genes (
     (
    seqname      STRING         COMMENT 'chromosome or scaffold name',
    source       STRING         COMMENT 'data source that generated this feature',
    feature      STRING         COMMENT 'feature type name, e.g. Gene, Variation, Similarity',
    start        INT            COMMENT 'start position of the feature, with sequence numbering starting at 1',
    end          INT            COMMENT 'end position of the feature, with sequence numbering starting at 1',
    score        INT            COMMENT 'floating point value',
    strand       STRING         COMMENT '+ (forward) or - (reverse)',
    frame        INT            COMMENT '0, 1 or 2. 0 indicates first base is the first base of a codon, 1 second base is the first base of a codon, etc', 
    attribute    STRING         COMMENT 'List of Exon start positions',
    exonEnds     INT            COMMENT 'semicolon-separated list of additional info'
    )
COMMENT 'Ensembl hg19 gene annotations from ftp://ftp.ensembl.org/pub/release-74/gtf/homo_sapiens/Homo_sapiens.GRCh37.74.gtf.gz'
```