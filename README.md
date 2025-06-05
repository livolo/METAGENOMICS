# METAGENOMICS Reprogramming 
<b>Characterize Metabolic Alterations in Cisplatin-Resistant vs. Sensitive OSCC</b>
The resources and references used to build this tutorial are found at the bottom, in the <link>resources</link> section. 

# WORKFLOW 
Step 1: Identify or Obtain Relevant Data <br> 
Tools & Resources: <br>
NCBI GEO – Gene expression datasets <br>
Search using keywords: "cisplatin resistant OSCC RNA-seq" or "OSCC cisplatin resistance metabolomics" <br>

Step 2: Preprocess the RNA-seq Data <br> 
Tools: <br>
FASTQC – Quality check for raw FASTQ files <br>
Trimmomatic – Adapter trimming (optional)<br> 
HISAT2 – Read alignment to human genome (GRCh38) <br>
featureCounts– Generate gene count matrix<br> 
Align reads and generate a gene count matrix<br> 
Proceed to normalization & DE analysis<br> 

Step 3: Differential Gene Expression Analysis
<br>
Tools: <br> 
DESeq2 (R/Bioconductor) <br> 
Compare gene expression: Resistant vs. Sensitive <br>
Export significantly changed genes (log2FC > 1, adj. p < 0.05)<br> 

Step 4: Pathway & Enrichment Analysis (Focus on Metabolism) <br>
Tools:<br> 
Enrichr or GSEA <br>
MetaboAnalyst (integrates metabolomics + gene expression)<br> 
Focus on:<br> 
Glycolysis/Gluconeogenesis,
TCA Cycle,
Glutaminolysis, 
Fatty acid metabolism, 
Oxidative phosphorylation. 
<br>
 
Step 5: (Optional) Integrate Metabolomics Data <br>
If available, integrate with transcriptomics to enhance insight.<br> 
Tools:<br> 
MetaboAnalyst (Joint Pathway Analysis)<br>

Step 6: Visualize the Results <br>
Tools: <br>
R or Python (ggplot2, seaborn, matplotlib)