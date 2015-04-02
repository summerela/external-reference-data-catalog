##RefSeq Gene Definitions
The Reference Sequence (RefSeq) collection provides a comprehensive, integrated, non-redundant, well-annotated set of sequences, including genomic DNA, transcripts, and proteins. RefSeq sequences form a foundation for medical, functional, and diversity studies.


Match_On|Downloads|Sample_Query|Notes|
|------------|---------|--------------|------------|-----|
|chrom<br>strand<br>txStart<br>txEnd<br>cdsStart<br>cdsEnd<br>exonCount<br>exonStarts<br>exonEnds|[hg19](http://hgdownload.cse.ucsc.edu/goldenPath/hg19/database/refFlat.txt.gz)<br>[Recent release](http://hgdownload.cse.ucsc.edu/goldenPath/currentGenomes/Homo_sapiens/database/refFlat.txt.gz)|tbd|[Chromosome mapping](http://ftp.ncbi.nlm.nih.gov/genomes/H_sapiens/ARCHIVE/ANNOTATION_RELEASE.105/Assembled_chromosomes/chr_accessions_GRCh37.p13)<br>The
top_level.gff3 and chr_accessions files must be mapped to get complete
positional information.|

##RefSeq Database Schema
```Mysql
CREATE TABLE refseq_hg19
    (
    seqid       STRING           COMMENT 'NCBI RefSeq ID',
    source      STRING           COMMENT 'Annotation source',
    type        STRING           COMMENT 'Feature type',
    start       INT              COMMENT '1-based start position',
    end         INT              COMMENT '1-based end position',
    score       INT              COMMENT 'Feature score',
    strand      STRING           COMMENT 'Strand of feature',
    phase       STRING           COMMENT 'For CDS features, indicates start in relation to reading frame',
    ID          STRING           COMMENT 'Unique feature ID',
    Name        STRING           COMMENT 'Feature display name',
    Dbxref      STRING           COMMENT 'Database cross reference',
    chromosome  STRING           COMMENT 'Unique identifier for each (known gene, alignment position) pair',
    gbkey
genome
mol_type
description
gene
part
pseudo
    Parent      STRING           COMMENT 'Parent of feature for grouping exons into transcripts, etc.',
product
transcript_id
gene_synonym
partial
ncrna_class
protein_id
exon_number
    Note        STRING      COMMENT 'A free text note',
exception
transl_except
anticodon
Target
e_value
bit_score
num_ident
blast_aligner
pct_identity_gap
num_mismatch
pct_identity_ungap
gap_count
pct_coverage
pct_coverage_hiqual
pct_identity_gapopen_only
common_component
filter_score
weighted_identity
rank
assembly_bases_seq
assembly_bases_aln
for_remapping
matched_bases
matchable_bases
lxr_locAcc_currStat_120
    Gap             INT           COMMENT 'The alignment of the feature to the target if the two are not collinear (e.g. contain gaps)',
matches
identity
splices
consensus_splices
product_coverage
exon_identity
idty
merge_aligner
map
lxr_locAcc_currStat_35
inversion_merge_aligner
    Is_circular     STRING           COMMENT 'Flag to indicate ciruclar features',
country
isolation-source
note
tissue-type
codons
transl_table

    )
COMMENT 'RefSeq gene annotations for GRCh37 from ftp://ftp.ncbi.nlm.nih.gov/refseq/H_sapiens/H_sapiens/ARCHIVE/ANNOTATION_RELEASE.105/GFF/ref_GRCh37.p13_top_level.gff3.gz'
						    ```
