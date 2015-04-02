# External Reference Data Catalog

A catolog of external references available in the impala database.  

This README provides a summary of available resources. Click on a link to view more information about each database, including information about how to map information between databases and sample queries.  

##Gene definition resources
Annotate variants with gene definitions based upon genomic location. Use these files to find exact matches with a variant based on chromosome, start, stop, reference and alternate alleles. 

<ul>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/ensembl_genedefs.md", target="_blank">Ensembl gene definitions</a></li>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/refseq_genedefs.md", target="_blank">RefSeq gene definitions</a></li>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/UCSC_genedefs.md", target="_blank">UCSC gene definitions</a></li>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/uniprot_genedefs.md", target="_blank">Uniprot gene definitions</a></li>
</ul>

##Regional resources
Functional annotation resources can be used to find overlap between a variant and a region in one of the following resources to determine if a mutation causes any disruption in function. Matching on these databases does not require an exact match, but instead checks to see if a variant falls within a region of interest. 
<ul>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/cytoband.md", target="blank">Cytobands</a>: Determine if variants are located on a cytogenic band</li>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/cpg.md", target="blank">CpG islands</a>: Determine if variant falls within a CpG island as determined by illumina 450 methylation array</li>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/dgv.md", target="blank">Database of Genomic Variants</a>: identify previously reported structural variants</li>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/encod.md", target="blank">ENCODE</a>: identify variants that disrupt promoter, enhancer, elongation and repressor regions</li>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/gap.md", target="blank">Gap positions</a>: determine if variant falls in a gap region</li>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/omim.md", target="blank">OMIM</a>: determine if variant falls in a region associated with specific human diseases.</li>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/pfam.md", target="blank">PFAM</a>: identify if variant falls within a specific protein family. </li>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/seg_dups.md", target="blank">Segmental duplications (GenomicSuperDups)</a>: find variants located in segmental duplications</li>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/gwas.md", target="blank">GWASCatalog</a>: determine if a variant has been reported in previously published GWAS</li>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/mirbase.md", target="blank">miRBase</a>: Find variants potentially disrupting microRNA</li>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/snobase.md", target="blank">snoRNABase</a>: Find variants potentially disrputing snoRNA</li>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/targetscans.md", target="blank">TargetScanS</a>: Locate variants potentially disrupting predicted microRNA binding sites</li>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/transfac.md", target="blank">Transfac Matrix Database</a>: Determine if variants are located in a transcription factor binding site</li>
</ul>

##Position-based Resources
The following resources can be used to compare a variant with available resources based upon an exact match between chromosome, start,stop and in most cases ref/alt alleles.  
<ul>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/admix.md", target="blank">Admix</a>: 1000 genomes? ExAc? still figuring out best method for calcualtion</li>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/cadd.md", target="blank">CADD (Combined Annotation Dependent Depletion)</a>: provides a score based on SVM of other multiple scores for each possible mutation in the human genome</li>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/cg.md", target="blank">CG (complete genomics) frequency annotations</a>: Use to filter out technical artificats by comparison with CG pipeline generated whole-genome data for a small group of healthy subjects.</li>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/clinvar.md", target="blank">Clinvar</a>: identify possible clinical significance of variants. </li>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/cosmic.md", target="blank">COSMIC (Catalogue Of Somatic Mutations In Cancer)</a>: find whether a mutation has been previously reported, in what cancer type, and frequency.</li>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/dann.md", target="blank">DANN</a>: uses the same feature set and training data as CADD to train a deep neural network (DNN).</li>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/dbsnp.md", target="blank">dbSNP</a>: Locate single base nucleotide subsitutions and short deletion and insertion polymorphisms</li>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/esp.md", target="blank">ESP exome sequencing</a>: identify genetic variants in exonic regions from over 6000 individuals </li>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/gerp.md", target="blank">GERP++</a>: Identifies constrained elements in multiple alignments by quantifying substitution deficits</li>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/go.md", target="blank">GO</a>: determine if a variant is linked to a specific GO term</li>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/interpro.md", target="blank">INTERPRO</a>: determine relation to functional predictions for proteins</li>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/kaviar.md", target="blank">KAVIAR</a>: determine variants have been reported already for a given specific genomic location.</li>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/kegg.md", target="blank">KEGG</a>: identify functional and pathway information.</li>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/phastcons.md", target="blank">phastCons</a>: Conserved Elements</li>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/polyphen.md", target="blank">PolyPhen2</a>: predict possible impact of an amino acid substitution on the structure and function of a human protein</li>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/repeatmasker.md", target="blank">RepeatMasker</a>: determine if variant falls in a region of low-complexity/highly repetetive region. </li>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/sift.md", target="blank">SIFT</a>: identify amino acid substitutions in protein-coding regions</li>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/simplerepeat.md", target="blank">SimpleRepeat</a>: identify variants located in tandem repeat regions.</li>
<li><a href="https://github.com/summerela/external-reference-data-catalog/blob/master/snp_array.md", target="blank">SNP array data</a>: determine which SNP's have observed variants on a particular platform.</li>
</ul>

