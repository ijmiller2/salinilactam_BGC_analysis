# salinilactam_BGC_analysis

This a git repository to document the analysis of slm pathway in the Marine Drugs review article "Interpreting Microbial Biosynthesis in the Genomic Age: Biological and Practical Considerations"


## example of Illumina HiSeq2500 sequencing simulation with ART_Illumina (v.2.5.1) and assembly with SPAdes (v.3.9.0)

art_illumina -p -ss HS25 -l 125 -f 100 -o len125_cov100_simulated_reads -m 275 -s 90 -i GCA_000016425.1_ASM1642v1_genomic.fna

gzip *.fq
gzip *.aln

spades.py -1 len125_cov100_simulated_reads1.fq.gz -2 len125_cov100_simulated_reads2.fq.gz -t 16 -m 16 -o Salinospora_tropica_len125_cov100_spades_asm

# example of how to run calculate_pathway_fragmentation.py

calculate_pathway_fragmentation.py -a len125_cov100_scaffolds.fasta -r GCA_000016425.1_ASM1642v1_genomic.fna -p s_tropica_cluster_coordinates.tab

