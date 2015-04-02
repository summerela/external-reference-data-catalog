##Uniprot Gene Definitions
The UniProt Knowledgebase (UniProtKB) provides the central database of protein sequences with accurate, consistent, rich sequence and functional annotation.

Match_On|Downloads|Sample_Query|Notes|
|------------|---------|--------------|------------|-----|
chrom<br>strand<br>txStart<br>txEnd<br>cdsStart<br>cdsEnd<br>exonCount<br>exonStarts<br>exonEnds|[hg19](http://ftp.uniprot.org/pub/databases/uniprot/previous_major_releases/release-2014_04/knowledgebase/uniprot_sprot-only2014_04.tar.gz)<br>[Recent release](http://http.uniprot.org/pub/databases/uniprot/current_release/knowledgebase/taxonomic_divisions/uniprot_sprot_human.dat.gz)|tbd|[Documentation](http://web.expasy.org/docs/userman.html) <br><br> Latest download links to most recent human reference build.|

##Uniprot Database Schema
```Mysql
CREATE TABLE uniprot_hg19
(
entry_name                 STRING                 COMMENT 'SwissProt entry name of the sequence',
status                 STRING                 COMMENT 'Entry status',
molecule_length_aa                 INT                 COMMENT 'Length of molecule in amino acids',
primary_accession        STRING                 COMMENT 'Researchers who wish to cite entries in their publications should always use the primary accession number',
additional_accessions                 STRING                 COMMENT 'If an existing entry is split into two or more entries, the original accession numbers are retained in all the derived entries and a new primary accession number is added.',
date_integrated                 STRING                 COMMENT 'Date the entry first appeared in the database',
sequence_version                 STRING                 COMMENT 'Date when sequence was last modified',
entry_version                 STRING                 COMMENT 'Date when data other than the sequence was last modified',
description                 STRING                 COMMENT 'Recommended and alternative protein names',
gene_name                 STRING                 COMMENT 'Official gene name',
synonyms                 STRING                 COMMENT 'Other gene names'
ordered_locus_names                 STRING                 COMMENT 'OLN, ORF numbers, CDS numbers or Gene numbers',
orf_name                 STRING                 COMMENT 'sequencing names or contig names or temporary ORFNames',
organelle                 STRING                 COMMENT 'Indicates if the gene coding for a protein originates from mitochondria, a plastid, a nucleomorph or a plasmid',
organism_taxonomy_crossref                 STRING                 COMMENT 'Identifier of a specific organism in a taxonomic database',
organism_host                 STRING                 COMMENT 'Indicates the host organism(s) that are susceptible to be infected by a virus'
reference_number                 INT                 COMMENT 'Sequential number to each reference citation in an entry', ##REMOVE? 
reference_position                 STRING                 COMMENT 'describe the extent of the work relevant to the entry carried out by the authors',
ref_strain                 STRING                 COMMENT 'Reference strain info',
ref_plasmid                 STRING                 COMMENT 'Refrence plasmid info',
ref_transposon                 STRING                 COMMENT 'Reference transposon info'
ref_tissue                 STRING                 COMMENT 'Reference tissue',
medline_crossref                 STRING                 COMMENT 'Eight-digit MEDLINE Unique Identifier (UI)',
pubmed_crossref                STRING                 COMMENT 'PubMed Unique Identifier (PMID)',
doi_crossref                 STRING                 COMMENT 'Digital Object Identifier (DOI)',
agricola_crossref                 STRING                 COMMENT 'AGRICOLA Unique Identifier',
reference_group                 STRING                 COMMENT 'Consortium name associated with a given citation',
reference_author                 STRING                 COMMENT 'Authors of the paper ',
reference_title                 STRING                 COMMENT 'Title of the paper (or other work) cited',
reference_location                 STRING                 COMMENT 'Conventional citation information for the reference',
allergen                 STRING                 COMMENT 'Information relevant to allergenic proteins',
alternative_products                 STRING                 COMMENT 'Description of the existence of related protein sequence(s) produced by alternative splicing of the same gene, alternative promoter usage, ribosomal frameshifting or by the use of alternative initiation codons',
biophysiochemical_properties                 STRING                 COMMENT 'Description of the information relevant to biophysical and physicochemical data and information on pH dependence, temperature dependence, kinetic parameters, redox potentials, and maximal absorption',
biotechnology                 STRING                 COMMENT 'Description of the use of a specific protein in a biotechnological process',
catalytic_activity                 STRING                 COMMENT 'Description of the reaction(s) catalyzed by an enzyme',
caution                 STRING                 COMMENT 'Warning about possible errors and/or grounds for confusion',
cofactor                 STRING                 COMMENT 'Description of any non-protein substance required by an enzyme for its catalytic activity',
developmental_stage                 STRING                 COMMENT 'Description of the developmentally-specific expression of mRNA or protein',
disease                  STRING                 COMMENT 'Description of the disease(s) associated with a deficiency of a protein',
disruption_phenotype                 STRING                 COMMENT 'Description of the effects caused by the disruption of the gene coding for the protein',
domain                 STRING                 COMMENT 'Description of the domain structure of a protein',
enzyme_regulation                 STRING                 COMMENT 'Description of an enzyme regulatory mechanism',
function                 STRING                 COMMENT 'General description of the function(s) of a protein',
induction                 STRING                 COMMENT 'Description of the compound(s) or condition(s) that regulate gene expression',
interaction                 STRING                 COMMENT 'Conveys information relevant to binary protein-protein interaction',
mass_spec                 STRING                 COMMENT 'Reports the exact molecular weight of a protein or part of a protein as determined by mass spectrometric methods',
misc                 STRING                 COMMENT 'Any comment which does not belong to any of the other defined topics',
pathway                 STRING                 COMMENT 'Description of the metabolic pathway(s) with which a protein is associated',
pharmaceutical                 STRING                 COMMENT 'Description of the use of a protein as a pharmaceutical drug',
polymorphism                 STRING                 COMMENT 'Description of polymorphism(s)',
ptm                 STRING                 COMMENT 'Description of any chemical alternation of a polypeptide, lines up with feature table info',
rna_editing                 STRING                 COMMENT 'Description of any type of RNA editing that leads to one or more amino acid changes',
sequence_caution                 STRING                 COMMENT 'Description of protein sequence reports that differ from the sequence that is shown in UniProtKB due to conflicts that are not described in FT CONFLICT lines, such as frameshifts, erroneous gene model predictions, etc',
similarity                 STRING                 COMMENT 'Description of the similaritie(s) (sequence or structural) of a protein with other proteins',
subcellular_location                 STRING                 COMMENT 'Description of the subcellular location of the chain/peptide/isoform',
subunit                 STRING                 COMMENT 'Description of the quaternary structure of a protein and any kind of interactions with other proteins or protein complexes; except for receptor-ligand interactions, which are described in the topic FUNCTION',
tissue_specificity                 STRING                 COMMENT 'Description of the tissue-specific expression of mRNA or protein',
toxic_dose                 STRING                 COMMENT 'Description of the lethal dose (LD), paralytic dose (PD) or effective dose of a protein',
web_resource                 STRING                 COMMENT 'Description of a cross-reference to a network database/resource for a specific protein',
database_crossref                 STRING                 COMMENT 'Information in external data resources that is related to UniProtKB entries',
protein_existence                 STRING                 COMMENT 'Evidence that we currently have for the existence of a protein',
keyword                 STRING                 COMMENT 'Information that can be used to generate indexes of the sequence entries based on functional, structural, or other categories',
key_name                 STRING                 COMMENT 'A fixed abbreviation (of up to 8 characters) with a defined meaning',
start                 STRING                 COMMENT '1-based inclusive start point',
stop                 STRING                 COMMENT '1-based inclusive end point',
seq_description                 STRING                 COMMENT 'additional information about the feature',
ft_id                 STRING                 COMMENT 'Unique and stable feature identifier (FTId), which allows to construct links directly from position-specific annotation in the feature table to specialized protein-related databases',
seq_length_aa                 STRING                 COMMENT 'Sequence length in amino acids',
molecular_weight                 STRING                 COMMENT 'Molecular weight rounded to the nearest mass unit (Dalton)',
crc64                 STRING                 COMMENT 'Algorithm to compute the CRC64 is described in the ISO 3309 standard. The generator polynomial is x64 + x4 + x3 + x',
sequence                 STRING                 COMMENT 'Amino acids are the standard IUPAC one letter codes'
)
COMMENT 'Uniprot gene annotations for hg19 from ftp://ftp.uniprot.org/pub/databases/uniprot/previous_major_releases/release-2014_04/knowledgebase/uniprot_sprot-only2014_04.tar.gz'
```
