##Ensembl Gene Definitions
All annotated protein coding genes in the ensembl human gene set. 

|Downloads|Sample_Query|Notes|
|---------|--------------|------------|-----|
|[hg19](http://ftp.ensembl.org/pub/release-74/gtf/homo_sapiens/Homo_sapiens.GRCh37.74.gtf.gz)<br>[Recent release](http://ftp.ensembl.org/pub/current_gtf/homo_sapiens/Homo_sapiens.GRCh38.78.gtf.gz)|[Sample Illumina  Queries](https://github.com/summerela/external-reference-data-catalog/blob/master/ensembl_queries_illumina.md) <br> [Sample CGI Queries](https://github.com/summerela/external-reference-data-catalog/blob/master/ensembl_queries_cgi.md)|[Documentation](http://ftp.ensembl.org/pub/release-74/gtf/homo_sapiens/README)<br>Latest download links to most recent human reference build.|

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
