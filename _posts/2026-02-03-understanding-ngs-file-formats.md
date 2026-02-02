---
layout: post
title: "Understanding NGS File Formats: A Comprehensive Guide"
date: 2026-02-03
author: Pratik Chandrani
tags:
  - Bioinformatics
  - NGS
  - File Formats
  - Genomics
excerpt: A comprehensive guide to essential file formats used in Next-Generation Sequencing (NGS) analysis, including FASTQ, SAM/BAM, VCF, GTF/GFF3, and MAF.
---

Next-Generation Sequencing (NGS) has revolutionized genomics research and clinical diagnostics. Understanding the various file formats used in NGS data analysis is crucial for anyone working in bioinformatics or computational biology. This guide provides a comprehensive overview of the most important NGS file formats.

## FASTQ Format

### Overview

FASTQ is the standard format for storing both sequence data and corresponding quality scores from high-throughput sequencing platforms. It has become the de facto standard for raw sequencing data (Cock et al., 2010).

### Structure

Each sequence in a FASTQ file is represented by four lines:

```
@SEQ_ID
GATTTGGGGTTCAAAGCAGTATCGATCAAATAGTAAATCCATTTGTTCAACTCACAGTTT
+
!''*((((***+))%%%++)(%%%%).1***-+*''))**55CCF>>>>>>CCCCCCC65
```

1. **Line 1**: Begins with `@` followed by sequence identifier and optional description
2. **Line 2**: Raw sequence letters (A, C, G, T, N)
3. **Line 3**: Begins with `+` and optionally repeats the sequence identifier
4. **Line 4**: Quality scores encoded as ASCII characters

### Quality Scores

Quality scores represent the probability that a base call is incorrect. The Phred quality score Q is calculated as:

```
Q = -10 × log₁₀(P)
```

where P is the probability of an incorrect base call.

Common quality encodings:
- **Phred+33** (Sanger, Illumina 1.8+): ASCII 33-126
- **Phred+64** (Illumina 1.3-1.7): ASCII 64-126

### Applications

- Raw output from sequencing platforms
- Input for alignment and quality control tools
- Archival of sequencing data in public repositories

**Reference:** Cock, P. J., Fields, C. J., Goto, N., Heuer, M. L., & Rice, P. M. (2010). The Sanger FASTQ file format for sequences with quality scores, and the Solexa/Illumina FASTQ variants. *Nucleic Acids Research*, 38(6), 1767-1771.

---

## SAM/BAM Format

### Overview

The Sequence Alignment/Map (SAM) format and its binary counterpart (BAM) are standard formats for storing aligned sequencing reads (Li et al., 2009). BAM files are compressed, indexed versions of SAM files that enable efficient storage and rapid access.

### SAM Structure

SAM files consist of:

1. **Header section**: Metadata about reference sequences, read groups, and processing
2. **Alignment section**: One line per read alignment

### Mandatory Fields

Each alignment line contains 11 mandatory fields:

| Field | Name | Description |
|-------|------|-------------|
| 1 | QNAME | Query template name |
| 2 | FLAG | Bitwise flags (pairing, strand, mapping quality) |
| 3 | RNAME | Reference sequence name |
| 4 | POS | 1-based leftmost mapping position |
| 5 | MAPQ | Mapping quality |
| 6 | CIGAR | String describing alignment |
| 7 | RNEXT | Reference name of mate/next read |
| 8 | PNEXT | Position of mate/next read |
| 9 | TLEN | Template length |
| 10 | SEQ | Segment sequence |
| 11 | QUAL | Quality scores |

### CIGAR String

The CIGAR (Compact Idiosyncratic Gapped Alignment Report) string describes how a read aligns to the reference:

- **M**: Alignment match (can be sequence match or mismatch)
- **I**: Insertion to the reference
- **D**: Deletion from the reference
- **N**: Skipped region from the reference
- **S**: Soft clipping (clipped sequences present in SEQ)
- **H**: Hard clipping (clipped sequences NOT present in SEQ)
- **P**: Padding (silent deletion from padded reference)

Example: `10M2I5M` means 10 matches, 2 insertions, 5 matches

### BAM Format

BAM is the binary, compressed version of SAM:
- Significantly smaller file size (~4-5× compression)
- Indexed for rapid random access
- Can be sorted by coordinate or read name

### Applications

- Storage of aligned reads
- Variant calling input
- Visualization in genome browsers
- Coverage analysis

**Reference:** Li, H., Handsaker, B., Wysoker, A., Fennell, T., Ruan, J., Homer, N., ... & 1000 Genome Project Data Processing Subgroup. (2009). The Sequence Alignment/Map format and SAMtools. *Bioinformatics*, 25(16), 2078-2079.

---

## VCF Format

### Overview

The Variant Call Format (VCF) is a text format for storing genetic variation data, including SNPs, indels, and structural variants (Danecek et al., 2011). VCF has become the standard for representing and exchanging variant data.

### Structure

VCF files contain:

1. **Meta-information lines**: Begin with `##`, describe file format, contigs, filters, INFO fields, etc.
2. **Header line**: Begins with `#`, lists column names
3. **Data lines**: One variant per line

### Mandatory Columns

1. **CHROM**: Chromosome/contig name
2. **POS**: 1-based position
3. **ID**: Variant identifier (e.g., dbSNP rsID)
4. **REF**: Reference allele
5. **ALT**: Alternate allele(s)
6. **QUAL**: Phred-scaled quality score
7. **FILTER**: Filter status (PASS or reason for failure)
8. **INFO**: Additional information (semicolon-separated key=value pairs)
9. **FORMAT**: Format of genotype fields
10. **Sample columns**: One per sample

### Example

```
##fileformat=VCFv4.3
##reference=hg38
#CHROM  POS     ID      REF  ALT     QUAL  FILTER  INFO                    FORMAT  SAMPLE1
chr1    12345   rs123   A    G       30    PASS    DP=100;AF=0.5          GT:DP:GQ 0/1:50:30
chr2    67890   .       GT   G       50    PASS    DP=80;SVTYPE=DEL       GT:DP    1/1:80
```

### Common INFO Fields

- **DP**: Total depth of coverage
- **AF**: Allele frequency
- **AC**: Allele count
- **AN**: Total number of alleles
- **MQ**: RMS mapping quality

### Genotype Fields

- **GT**: Genotype (0/0, 0/1, 1/1, etc.)
- **DP**: Read depth
- **GQ**: Genotype quality
- **AD**: Allelic depths
- **PL**: Phred-scaled likelihoods

### Applications

- Variant calling output
- Annotation pipelines
- Population genetics studies
- Clinical variant interpretation
- Database submissions (e.g., ClinVar, dbSNP)

**Reference:** Danecek, P., Auton, A., Abecasis, G., Albers, C. A., Banks, E., DePristo, M. A., ... & 1000 Genomes Project Analysis Group. (2011). The variant call format and VCFtools. *Bioinformatics*, 27(15), 2156-2158.

---

## GTF/GFF3 Format

### Overview

Gene Transfer Format (GTF) and General Feature Format version 3 (GFF3) are used to describe genes and other genomic features. While similar, they have important differences (Eilbeck et al., 2005).

### GTF Format (GTF2.2)

GTF is a refinement of GFF2, commonly used in RNA-seq analysis. Each line has 9 tab-delimited fields:

1. **seqname**: Chromosome/contig name
2. **source**: Program that generated the feature
3. **feature**: Feature type (e.g., exon, CDS, gene)
4. **start**: 1-based start position
5. **end**: 1-based end position (inclusive)
6. **score**: Floating point value or `.`
7. **strand**: `+`, `-`, or `.`
8. **frame**: 0, 1, 2, or `.` for coding sequences
9. **attribute**: Semicolon-separated key-value pairs

### GTF Example

```
chr1  HAVANA  gene        11869  14409  .  +  .  gene_id "ENSG00000223972"; gene_name "DDX11L1";
chr1  HAVANA  transcript  11869  14409  .  +  .  gene_id "ENSG00000223972"; transcript_id "ENST00000456328";
chr1  HAVANA  exon        11869  12227  .  +  .  gene_id "ENSG00000223972"; transcript_id "ENST00000456328"; exon_number "1";
```

### GFF3 Format

GFF3 is more flexible and supports hierarchical relationships between features. Key differences from GTF:

- Uses `ID` and `Parent` attributes for hierarchical relationships
- Uses `=` instead of space in attributes
- Allows multi-valued attributes
- More standardized feature types from Sequence Ontology

### GFF3 Example

```
chr1  Ensembl  gene        11869  14409  .  +  .  ID=gene:ENSG00000223972;Name=DDX11L1;biotype=lincRNA
chr1  Ensembl  transcript  11869  14409  .  +  .  ID=transcript:ENST00000456328;Parent=gene:ENSG00000223972
chr1  Ensembl  exon        11869  12227  .  +  .  ID=exon:ENSE00002234944;Parent=transcript:ENST00000456328
```

### Applications

- Gene annotation
- RNA-seq quantification (e.g., with featureCounts, HTSeq)
- Genome browser visualization
- Functional genomics analysis

**Reference:** Eilbeck, K., Lewis, S. E., Mungall, C. J., Yandell, M., Stein, L., Durbin, R., & Ashburner, M. (2005). The Sequence Ontology: a tool for the unification of genome annotations. *Genome Biology*, 6(5), R44.

---

## MAF Format

### Overview

Multiple Alignment Format (MAF) has two main uses in genomics:

1. **Mutation Annotation Format**: Used by projects like TCGA for somatic mutation data
2. **Multiple Alignment Format**: Used by UCSC for storing multiple sequence alignments

### MAF for Mutations (TCGA/GDC)

The Mutation Annotation Format is tab-delimited and includes:

#### Core Columns

- **Hugo_Symbol**: Gene symbol
- **Chromosome**: Chromosome number
- **Start_Position**: 1-based start position
- **End_Position**: 1-based end position
- **Strand**: `+` or `-`
- **Variant_Classification**: Mutation type (Missense, Nonsense, Frameshift, etc.)
- **Variant_Type**: SNP, DNP, INS, DEL
- **Reference_Allele**: Reference allele
- **Tumor_Seq_Allele1**: Tumor allele 1
- **Tumor_Seq_Allele2**: Tumor allele 2
- **Tumor_Sample_Barcode**: Sample identifier

#### Additional Annotation Columns

- **dbSNP_RS**: dbSNP identifier
- **dbSNP_Val_Status**: Validation status
- **Protein_Change**: Amino acid change
- **Transcript_ID**: Ensembl or RefSeq transcript ID
- **Exon_Number**: Affected exon

### Example

```
Hugo_Symbol  Chromosome  Start_Position  End_Position  Variant_Classification  Reference_Allele  Tumor_Seq_Allele2
TP53         17          7577538         7577538       Missense_Mutation       C                 T
KRAS         12          25398284        25398284      Missense_Mutation       C                 A
```

### Applications

- Cancer genomics studies
- Somatic mutation databases (TCGA, ICGC)
- Mutation signature analysis
- Driver gene identification
- Clinical reporting

### MAF for Multiple Alignments (UCSC)

UCSC's MAF format stores pairwise or multiple alignments:

```
a score=23262.0
s hg38.chr7    27578828 38 + 158545518 ATGGCGTCAGATTGGGCGTGAACCTCCAGTGATTACACA
s panTro1.chr6 28741140 38 + 161576975 ATGGCGTCAGATTGGGCGTGAACCTCCAGTGATTACACA
```

Lines:
- **a**: Alignment header with score
- **s**: Sequence line (species, chromosome, start, size, strand, chr size, aligned sequence)

---

## Best Practices

### File Format Selection

- **FASTQ**: Raw sequencing data, quality control
- **BAM**: Aligned reads (always use BAM over SAM for storage)
- **VCF**: Variant calls, genotype data
- **GTF**: RNA-seq analysis, transcript quantification
- **GFF3**: Complex gene models, genome annotation
- **MAF**: Somatic mutations, comparative genomics

### Compression and Indexing

- Use **gzip** (.gz) for FASTQ, VCF, GTF/GFF3
- Use **bgzip** for VCF before tabix indexing
- Use **BAM** (already compressed) with `.bai` index
- Never compress BAM files with gzip

### Validation Tools

- **FASTQ**: FastQC, seqtk
- **SAM/BAM**: ValidateSamFile (Picard), samtools
- **VCF**: vcf-validator, bcftools
- **GTF/GFF**: gffread, GenomeTools

### Common Pitfalls

1. **Coordinate systems**: Remember that GTF/GFF use 1-based coordinates, while BED uses 0-based
2. **Encoding**: Ensure correct quality score encoding for FASTQ
3. **Sorting**: BAM files must be sorted before indexing
4. **Headers**: Always include proper headers in SAM/VCF files
5. **Validation**: Validate files before analysis to catch formatting errors

---

## Conclusion

Understanding these file formats is essential for NGS data analysis. Each format serves specific purposes in the bioinformatics workflow:

1. **FASTQ**: Starting point (raw reads)
2. **SAM/BAM**: Alignment results
3. **VCF**: Variant calls
4. **GTF/GFF3**: Feature annotation
5. **MAF**: Mutation summaries

Modern bioinformatics tools handle these formats efficiently, but knowing their structure helps in troubleshooting, developing custom scripts, and understanding tool requirements.

---

## References

1. Cock, P. J., Fields, C. J., Goto, N., Heuer, M. L., & Rice, P. M. (2010). The Sanger FASTQ file format for sequences with quality scores, and the Solexa/Illumina FASTQ variants. *Nucleic Acids Research*, 38(6), 1767-1771. https://doi.org/10.1093/nar/gkp1137

2. Li, H., Handsaker, B., Wysoker, A., Fennell, T., Ruan, J., Homer, N., ... & 1000 Genome Project Data Processing Subgroup. (2009). The Sequence Alignment/Map format and SAMtools. *Bioinformatics*, 25(16), 2078-2079. https://doi.org/10.1093/bioinformatics/btp352

3. Danecek, P., Auton, A., Abecasis, G., Albers, C. A., Banks, E., DePristo, M. A., ... & 1000 Genomes Project Analysis Group. (2011). The variant call format and VCFtools. *Bioinformatics*, 27(15), 2156-2158. https://doi.org/10.1093/bioinformatics/btr330

4. Eilbeck, K., Lewis, S. E., Mungall, C. J., Yandell, M., Stein, L., Durbin, R., & Ashburner, M. (2005). The Sequence Ontology: a tool for the unification of genome annotations. *Genome Biology*, 6(5), R44. https://doi.org/10.1186/gb-2005-6-5-r44

5. UCSC Genome Browser. Multiple Alignment Format (MAF). https://genome.ucsc.edu/FAQ/FAQformat.html#format5

6. National Cancer Institute GDC. Mutation Annotation Format (MAF) Specification. https://docs.gdc.cancer.gov/Data/File_Formats/MAF_Format/

---

*This post is part of our bioinformatics tutorial series. For questions or suggestions, please contact us through our lab website.*
