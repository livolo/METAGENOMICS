# METAGENOMICS Reprogramming 
<b>Characterize Metabolic Alterations in Cisplatin-Resistant vs. Sensitive OSCC</b>
The resources and references used to build this tutorial are found at the bottom, in the resources section. 

# WORKFLOW 
<b>Step 1: Identify or Obtain Relevant Data </b>
<br> 
Tools & Resources: <br>
NCBI GEO – Gene expression datasets 
link - "https://www.ncbi.nlm.nih.gov/geo/" <br>
Search using keywords: "cisplatin resistant OSCC RNA-seq" or "OSCC cisplatin resistance metabolomics" <br>

<b>Step 2: Preprocess the RNA-seq Data</b> <br> 
Tools: <br>
FASTQC – Quality check for raw FASTQ files <br>
Trimmomatic – Adapter trimming (optional)<br> 
HISAT2 – Read alignment to human genome (GRCh38) <br>
featureCounts– Generate gene count matrix<br> 
Align reads and generate a gene count matrix<br> 
Proceed to normalization & DE analysis<br> 

<b>Step 3: Differential Gene Expression Analysis</b>
<br>
Tools: <br> 
DESeq2 (R/Bioconductor) <br> 
Compare gene expression: Resistant vs. Sensitive <br>
Export significantly changed genes (log2FC > 1, adj. p < 0.05)<br> 

<b>Step 4: Pathway & Enrichment Analysis (Focus on Metabolism)</b> <br>
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
 
<b>Step 5: (Optional) Integrate Metabolomics Data</b> <br>
If available, integrate with transcriptomics to enhance insight.<br> 
Tools:<br> 
MetaboAnalyst (Joint Pathway Analysis)<br>

<b>Step 6: Visualize the Results</b> <br>
Tools: <br>
R or Python (ggplot2, seaborn, matplotlib)