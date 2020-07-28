# Variant_Calling_Pipeline
Example Variant Calling Pipeline with Genome Masking

Below Are Shell Scripts for Entire RNA-Seq Variant Calling Pipeline with Genome Masking. The pipeline is annotated with all the various
software utilized in the analysis and was built using GATK3.7. With the latest release of GATK modification of the code will need to
occur but the general idea is the same. 

Part 1. Initial Calling of Variants using GATK
qsub_FE_Muscle_Part1   (creates g.VCFs of ALL feed efficiency muscle samples)

Part 2. Merge All VCFs and Create a Masked Genome
qsub_Combined_VCFs_Part_2 (Combines ALL g.VCF files from both studies and tissues into one giant g.VCF file)
qsub_Masking_Genome_Part_2 (Script to create the masked genome using bedtools)

Part 3. Call Variants Using Masked Genome to Reduce Ref. Allele Bias
qsub_FE_Muscle_Part3_A  (Creates g.VCFs for all feed efficiency muscle samples--- had to break into parts A and B due to memory usage limitations on BioMix)
qsub_FE_Muscle_Part3_B
sbatch_Merge_FE_Muscle_Part3_C (Creates a combined g.VCF off all feed efficiency muscle samples---which was then analyzed using VADT)
