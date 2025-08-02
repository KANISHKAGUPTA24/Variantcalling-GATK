# NGS Variant Calling Pipeline using GATK
#Overview\
This project implements a complete germline variant calling pipeline based on the GATK  workflow for analyzing whole-genome sequencing (WGS) data. The goal is to identify high-quality single nucleotide polymorphisms (SNPs) and indels in human DNA sequences.\

#Dataset\
Source: 1000 Genomes Project – Phase 3\
Data format: Paired-end FASTQ files\
Sample reference genome: Human GRCh38/hg38\

#Pipeline Steps\
1. Quality Control\
Tool: FastQC\
Purpose: Assess the quality of raw FASTQ files\
2. Read Alignment\
Tool: BWA-MEM\
Aligns raw reads to the human reference genome\
Output: SAM file\
3. File Conversion & Sorting\
Tool: Samtools\
Converts SAM → BAM, sorts and indexes BAM files\
4. Mark Duplicates\
Tool: GATK MarkDuplicates\
Removes PCR duplicates to prevent false positives\
5. Base Quality Score Recalibration (BQSR)\
Tools: GATK BaseRecalibrator and ApplyBQSR\
Adjusts base quality scores to reduce technical bias\
6. Variant Calling\
Tool: GATK HaplotypeCaller\
Generates GVCF file with potential variants\
7. Variant Filtration\
Tool: GATK VariantFiltration\
Applies quality thresholds to SNPs and indels\
8. Variant Annotation\
Tool: VCFtools and online tools such as Ensembl VEP\
Annotates variants for downstream interpretation\

#Output\
Filtered and annotated VCF file\
Intermediate BAM and recalibrated BAM files\

