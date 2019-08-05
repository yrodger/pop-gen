#File conversion resources

As population geneticists, we spend an awful amount of time converting file formats. Here are a couple of tools I found useful.

##PGDSpider

PGDSpider (http://www.cmpg.unibe.ch/software/PGDSpider/)
is a widely known software that allows for easy conversion between common file formats such as STRUCTURE, GENEPOP, ARELQUIN, etc. The user is
asked to specify details about the input and output file formats.
Here's an example of a "spid" file I created for converting from STRUCTURE to GENEPOP format (**answers in bold**):

> spid-file generated: Wed Apr 17 11:25:07 AEST 2019

> STRUCTURE Parser questions
> PARSER_FORMAT=STRUCTURE

> What is the ploidy of the data?
> STRUCTURE_PARSER_PLOIDY_QUESTION=**DIPLOID_TWO_ROWS**
> Select the type of the data:
> STRUCTURE_PARSER_DATA_TYPE_QUESTION=**SNP**
> Enter the number of markers (loci) listed in the input file:
> STRUCTURE_PARSER_NUMBER_LOCI_QUESTION=**13016**
> Are marker (locus) names included?
> STRUCTURE_PARSER_LOCI_NAMES_QUESTION=**true**
> How are Microsat alleles coded?
> STRUCTURE_PARSER_MICROSAT_CODING_QUESTION=**ARBITARY**
> Enter the size of the repeated motif (same for all loci: one number; different: comma separated list (e.g.: 2,2,3,2):
> STRUCTURE_PARSER_REPEAT_SIZE_QUESTION=
> What is the missing value code (-9, -999, ...):
> STRUCTURE_PARSER_MISSING_CODE_QUESTION=**-9**
> Is the "PopData" column (population identifier) present in the input file?
> STRUCTURE_PARSER_POP_DATA_PRESENT_QUESTION=**true**
> Is the "Phase Information" row present?
> STRUCTURE_PARSER_PHASE_ROW_QUESTION=**false**
> Are individual names (labels) included in the input file?
> STRUCTURE_PARSER_IND_NAMES_QUESTION=**true**
> Are the "Recessive Alleles" row and/or the "Inter-Marker Distance" row present in the input file?
> STRUCTURE_PARSER_ADDITIONAL_ROW_QUESTION=**NONE**

> GENEPOP Writer questions
> WRITER_FORMAT=GENEPOP

> Specify which data type should be included in the GENEPOP file  (GENEPOP can only analyze one data type per file):
> GENEPOP_WRITER_DATA_TYPE_QUESTION=**SNP**
> Specify the locus/locus combination you want to write to the GENEPOP file:
> GENEPOP_WRITER_LOCUS_COMBINATION_QUESTION=

##genomic_converter

