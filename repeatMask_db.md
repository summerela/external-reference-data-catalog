##RepeatMasker
|Description|Format|Lookup|Match_Fields|hg19_download|latest_release|Notes|
|-----------|------|------|------------|---------|---------------|--------------|-----|
|RepeatMasker repeat and low-complexity regions|tsv|direct|query_sequence<br>position in query begin<br>position in query end|[hg19](http://www.repeatmasker.org/genomes/hg19/RepeatMasker-rm405-db20140131/hg19.fa.out.gz)|[Recent release](http://www.repeatmasker.org/genomes/hg38/RepeatMasker-rm405-db20140131/hg38.fa.out.gz)|<ul><li>Latest download links to most recent human reference</li><li>Match on query or repeat</li></ul>|

##RepeatMasker Database Schema
```Mysql
CREATE TABLE repeat_masker
   (
    SW Score                    INT         COMMENT 'Smith-Waterman score of the match',
 perc div.                   INT         COMMENT 'pct substitutions in matching region compared to consensus',
 perc del.                   INT         COMMENT 'pct of bases opposite a gap in the query sequence (deleted bp)',
 perc ins.                   INT         COMMENT 'pct of bases opposite a gap in the query sequence (deleted bp)',
 query sequence              STRING      COMMENT 'chromosome or query name',
    position in query begin     INT         COMMENT 'starting position of match in query sequence',
    position in query end       INT         COMMENT 'ending position of match in query sequence',
    (left)                      INT         COMMENT 'no. of bases in query sequence past the ending position of match',
    matching repeat             STRING      COMMENT 'C=match is complement of consensus, also can = + or - strand',
    repeat class/family         STRING      COMMENT 'name of the matching interspersed repeat',
    position in repeat begin    INT         COMMENT 'starting position of match in database sequence (using top-strand numbering)',
    position in repeat end      INT         COMMENT 'ending position of match in database sequence',
    repeat (left)               INT         COMMENT 'no. of bases in complement of repeat consensus seq prior to beginning of the match. 0 = match extended to end of repeat consensus seq',
    ID                          INT         COMMENT 'repeat mask db ID'
    )
COMMENT 'Repeat Library 20140131 from http://www.repeatmasker.org/genomes/hg19/RepeatMasker-rm405-db20140131/hg19.fa.out.gz'
```
						    
