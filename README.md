Exome and WGS
This section focused on genome sequence alignment. A simulated single-end 100bp reads 
was aligned and compared with the large, annotated reference genome using two different 
aligners, Bowtie and BWA. Firstly, an index file was built for the reference genome using either 
Bowtie or BWA. Then, the short reads were aligned to the index file using either Bowtie or BWA, 
and the results were saved to a SAM file. For the later SNPs calling analysis, the SAM file was 
converted to a compressed, fast-readable BAM file using the Samtools, and then sorted and 
indexed as required. Subsequently, we need to locate all the SNPs using Samtools. The same 
reference genome was indexed, and all SNPs were found, and the result was piped and 
converted to a binary format .bcf file using bcftools

Transcriptome
In this section, we are interested to see if the gene expression is different between two 
100 bp RNAseq reads from two different tissues of one individual. Firstly, a Bowtie index was 
created, and two reads were aligned to the reference genome using Tophat. Based on the 
alignment result, the Cufflinks tool helped to assemble transcripts separately, and merged the 
two transcript assemblies into a unified transcriptome. Merged transcriptome was compared
with the reference genome to assess the quality of the assembly. 

De Novo Assembly
3 datasets containing different length and number of reads were provided and the objective 
of this section is to assemble the reads to a complete genome from these reads. First, hash sets
with different hash lengths were created by velvet using one dataset or combination of short 
reads and long reads datasets. All sequencing reads were segmented into smaller fragments
(k-mer). Then, velvet helped to identify overlaps of k-1 bases between k-mers. If such an 
overlap is found, the corresponding nodes are connected, and adjacent k-mers are merged in 
sequence. Perform velvetg with different hash lengths until the satisfying assembly output is 
generated. 
