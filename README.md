# Abalign: a comprehensive multiple sequence alignment platform for B cell receptor immune repertoires


## Introduce

&emsp;&emsp; Multiple sequence alignment (MSA) has long been used as a powerful method to investigate the evolutionary, structural and functional properties of protein families. It is also a fundamental technique in recent deep-learning based protein 3D structure predictors. Though existing MSA methods have been well-established, they are not suitable for high-throughput computation, and do not fulfill the needs of processing BCRs or antibody sequences, because the highly variable regions cannot be well aligned, without the prior knowledge of gene recombination and hypermutation in antibody maturation. To our knowledge, no MSA tool is particularly designed for BCR alignment up to day. To address this issue, we developed Abalign, which is a high-throughput and accurate MSA tool based on AbRSA. Abalign incorporated the heuristic knowledge of antibody numberings, including IMGT, Kabat, Chothia and Martin, and follows the well-characterized patterns of conserved and insertion positions by immunology studies, which enable the result to be consistent with the structural and immunological knowledge.

&emsp;&emsp; We compared Abalign with three state-of-the-art MSA tools: Clustal Omega, MAFFT, MUSLCE. Comprehensive benchmark tests showed that Abalign outperformed the existing MSA tools in accuracy, speed and memory consumption significantly. Users can see detailed test information on the homepage of Abalign. Abalign was implemented in a user-friendly stand-alone program with interactive and visual interfaces, which support the multiple sequence alignment, as well as clustering, antibody numbering, delimiting CDR, constructing phylogenetic tree, VJ gene determination, clonotype analysis, aiding humanization, comparing BCR immune repertoires, etc. by just clicking the buttons. In addition, it supports the cross-analysis of multiple B cell receptor immune repertoire data to investigate information like shared clonotypes, or residue preferences, etc. Abalign can complete the alignment and analysis of 1 GB DNA FASTA files at a very fast speed on a PC with only 16GB RAM. Abalign will profit immunoinformatic and pharmaceutical communities by analyzing massive BCRs or antibodies and making new discoveries.


## Usage

&emsp;&emsp; Read USER_MANUAL.pdf from Code for details

## Download

&emsp;&emsp; Download the version you need from Release (Linux/Windows/macOS_x86)

## Authors

&emsp;&emsp; This software is developed by Cao Lab, Sichuan University. The main developers are Fanjie Zong, Chenyu Long, Wanxin Hu, and Yang Cao. If you have any opinions or suggestions, please contact cy_scu@yeah.net. 
