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
Trimmomatic – Adapter trimming<br> 
HISAT2 – Read alignment to human genome (GRCh38) <br>
featureCounts– Generate gene count matrix<br> 
Align reads and generate a gene count matrix<br> 
Proceed to normalization & DE analysis<br> 


<b>Step 3: Differential Gene Expression Analysis performed in goole Colab </b>
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
| Pathway                                              | Total | Expected | Hits | Raw p         | #NAME?   | Holm adjust | FDR         | Impact   |
|------------------------------------------------------|------:|---------:|-----:|--------------:|---------:|------------:|------------:|---------:|
| Glycerolipid metabolism                              | 34    | 13.905   | 45   | 6.19E-19      | 18.209   | 5.01E-17    | 5.01E-17    | 1.3333   |
| Lysine degradation                                   | 57    | 23.311   | 54   | 3.09E-18      | 17.51    | 2.47E-16    | 1.25E-16    | 1.1429   |
| Glycerophospholipid metabolism                       | 87    | 35.58    | 68   | 6.38E-13      | 12.195   | 5.04E-11    | 1.72E-11    | 1.0581   |
| Inositol phosphate metabolism                        | 69    | 28.219   | 54   | 1.61E-10      | 9.7929   | 1.24E-08    | 2.61E-09    | 1.1324   |
| Glycolysis or Gluconeogenesis                        | 60    | 24.538   | 40   | 4.05E-05      | 4.3928   | 0.003076    | 0.00052378  | 1.8136   |
| Ether lipid metabolism                               | 40    | 16.359   | 29   | 4.53E-05      | 4.3442   | 0.0033949   | 0.00052378  | 0.82051  |
| Drug metabolism - other enzymes                      | 70    | 28.628   | 45   | 5.30E-05      | 4.2753   | 0.0039256   | 0.00053712  | 0.76812  |
| Glutathione metabolism                               | 57    | 23.311   | 38   | 6.34E-05      | 4.1981   | 0.0046265   | 0.00057039  | 1.1429   |
| Pyruvate metabolism                                  | 48    | 19.63    | 30   | 0.0018796     | 2.7259   | 0.13533     | 0.01463     | 1.6383   |
| Nitrogen metabolism                                  | 10    | 4.0896   | 9    | 0.0019868     | 2.7018   | 0.14106     | 0.01463     | 1.1111   |
| Ascorbate and aldarate metabolism                    | 17    | 6.9524   | 13   | 0.0031026     | 2.5083   | 0.21718     | 0.020942    | 1.25     |
| Citrate cycle (TCA cycle)                            | 42    | 17.177   | 26   | 0.0045299     | 2.3439   | 0.31257     | 0.028225    | 2.1463   |
| Fructose and mannose metabolism                      | 40    | 16.359   | 24   | 0.010882      | 1.9633   | 0.74        | 0.062963    | 1.2821   |
<br>

![path_view_0_dpi72](c:\Users\kirti\OneDrive\Documents\Desktop\project metabolite\photo\path_view_0_dpi72.pdf)

<b>Step 5: Integrate Metabolomics Data</b> <br>
If available, integrate with transcriptomics to enhance insight.<br> 
Tools:<br> 
MetaboAnalyst (Joint Pathway Analysis)<br>


<b>Step 6: Visualize the Results</b> <br>
Tools: <br>
R or Python (ggplot2, seaborn, matplotlib)