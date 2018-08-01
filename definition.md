**Version**

VERSION: 1.0

**Description**

Lines beginning with '##' are directives (sometimes called pragmas or meta-data) and provide meta-information about the document as a whole. Blank lines should be ignored by parsers and lines beginning with a single '#' are used for human-readable comments and can be ignored by parsers

In addition, the following characters have reserved meanings in column 9 and must be escaped when used in other contexts:

; semicolon (%3B)
= equals (%3D)
& ampersand (%26)
, comma (%2C)


Please add description for each columns/attribute (R:required, O:optional)

## Header
* header:
  * (R) small RNA GFF version `## VERSION: 1.0`
  * (R) database: `##source-ontology` using FAIRSharing.org:
    * miRBase: (FAIRsharing) doi:10.25504/fairsharing.hmgte8
    * mirGeneDB: http://mirgenedb.org
  * (O) commands used to generate the file. At least information about adapter removal, filtering, aligner, mirna tool. All of them starting like: `## CMD: `. Can be multiple lines starting with this tag.
  *  (O) genome/database version used (maybe try to get from BAM file if GFF3 generated from it): `## REFERENCE:`
  * (R) sample names used in attribute:Expression: `## COLDATA:` separated by spaces
  * (O) Filter tags meaning: See Filter attribute below. Different filter tags should be separated by `,` character. Example: `## FILTER: ` and example would be `## FILTER: PASS(is ok), REJECT(false positive), REJECT lowcount(rejected due to low count in data)`.

## Columns

* (R) column1: seqID: precursor name
* (R) column2: source: databases used for the annotation with version (miRBase21, mirGeneDB2.0, ...etc): https://github.com/miRTop/incubator/issues/13. With the version: `mirbase21`
* (R) column3: type: `ref_miRNA, isomiR`: https://github.com/miRTop/incubator/issues/13  (SO:0002166 ref_miRNA and SO:0002167 isomiR)
* (R) column4/5: start/end: precursor start/end as indicated by alignment tool
* (O) column6: score (Optional): It can be the mapping score or any other score the tool wants to assign to the sequence.
* (R) column7: strand. In the case of mapping against precursor should be always `+`. It should accept mapping against the genome: `+/-` allowed.
* (O) column8: phase: (For features of type "CDS", the phase indicates where the feature begins with reference to the reading frame): Not relevant righ now. This can be: `.`
* (R) column9: attributes:
  * (R) UID: unique ID based on sequence like mintmap has for tRNA: prefix-22-BZBZOS4Y1 (https://github.com/TJU-CMC-Org/MINTmap/tree/master/MINTplates). good way to use it as cross-mapper ID between different naming or future changes. Currently supported by [mirtop](https://github.com/miRTop/mirtop/blob/dev/mirtop/mirna/realign.py#) code.
  * (O) Read: read name
  * (R) Name: mature name
  * (R) Parent: hairpin precursor name
  * (R) Variant: (categorical types - adapted from isomiR-SEA)
    * `iso_5p:+/-N`. `+` indicates extra nucleotides not in the reference miRNA. `-` indicates removed nucleotides not in the sequence. `N` the number of nucleotides of difference. For instance, if the sequence starts 2 nts after the reference miRNA, the label will be: `iso_5p:-2`, but if it starts before, the label will be `iso_5p:+2`.
    * `iso_3p:+/-N`. Same explanation applied.
    * `iso_add:+N`. Same explanation applied.
    * `iso_snp_seed`: when affected nucleotides are between [2-7].
    * `iso_snp_central_offset`: when affected nucleotides is at position [8].
    * `iso_snp_central`: when affected nucleotides are betweem [9-12].
    * `iso_snp_central_supp`: when affected nucleotides are betweem [13-17].
    * `iso_snp`: anything else.
  * (O) Changes (optional): similar to previous one but indicating the nucleotides being changed.
    * additions are in capital case
    * deletions are in lower case
    * example: `Changes iso_5p:0,iso_3p:TT,iso_add:GTC,iso_snp:0` where `Variant iso_add:+3,iso_3p:-2`.
  * (R) Cigar: CIGAR string as indicated [here](https://samtools.github.io/hts-specs/SAMv1.pdf). It is the standard CIGAR for aligners. With the restriction that `M` means exact match always. That's a difference with some aligners where `M` includes mismatches. In this case, if there is a mismatch, then it should be output like: `11MA7M` to indicates there is a mismatch at position 12, where `A` is the reference nucleotide.
  * (R) Hits: number of hits in the database.
  * (O) Alias (Optional): get names from miRBase/miRgeneDB or other database separated by `,`
  * (O) Genomic (Optional): positions on the genome in the following format: `chr:start-end,chr:start-end`
  * (R) Expression: raw counts separated by `,`. It should be in the same order than `colData` in the header.
  * (R) Filter: PASS or REJECT (this allow to keep all the data and select the one you really want to consider as valid features). PASS can have subclasses: `PASS:ignore`: meaning the sequence pass but the tools consider the variants showed here not reliable. `REJECT` can go with any short word explaining why it was rejected: `REJECT:lowcounts`. In this case the sequence will be skipped for data mining of the file when quering counts or summarize miRNA expression.
  * (O) Seed_fam (Optional): in the format of 2-8 nts and reference miRNA sharing the seed. Useful to go for pre-computed target predictions: `ATGCTGT:mir34a_5p`
