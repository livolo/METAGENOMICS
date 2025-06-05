# RNASEQ PIPELINE RUN IN LINUX MINT  

```bash
(base) kirti@kirti-Extensa-215-52:~/Desktop/project metabolite$ pwd 

/home/kirti/Desktop/project metabolite 

(base) kirti@kirti-Extensa-215-52:~/Desktop/project metabolite$ ls 

data                 RNAseqpipeline.sh          sratoolkit.3.2.1-ubuntu64.tar.gz  SRR_Acc_List.txt 

RNASeqpipelineOG.sh  sratoolkit.3.2.1-ubuntu64  SRR7621317_1.fastq                tmp 

(base) kirti@kirti-Extensa-215-52:~/Desktop/project metabolite$ ls -shl * 

4.0K -rw-rw-r-- 1 kirti kirti 1.2K May  6 15:05 RNASeqpipelineOG.sh 

4.0K -rw-rw-r-- 1 kirti kirti  227 May  6 17:32 RNAseqpipeline.sh 

89M -rw-rw-r-- 1 kirti kirti  89M May  6 15:52 sratoolkit.3.2.1-ubuntu64.tar.gz 

21M -rw-rw-r-- 1 kirti kirti  21M May  6 16:20 SRR7621317_1.fastq 

4.0K -rw-rw-r-- 1 kirti kirti  110 May  6 15:30 SRR_Acc_List.txt 

  

data: 

total 0 

  

sratoolkit.3.2.1-ubuntu64: 

total 72K 

4.0K drwxrwxr-x 3 kirti kirti 4.0K Mar 16 06:48 bin 

36K -rw-rw-r-- 1 kirti kirti  36K Mar 16 06:42 CHANGES 

4.0K drwxrwxr-x 3 kirti kirti 4.0K Mar 16 06:42 example 

4.0K -rw-rw-r-- 1 kirti kirti 1.7K Mar 16 06:42 README-blastn 

12K -rw-rw-r-- 1 kirti kirti  12K Mar 16 06:42 README.md 

8.0K -rw-rw-r-- 1 kirti kirti 4.9K Mar 16 06:42 README-vdb-config 

4.0K drwxrwxr-x 8 kirti kirti 4.0K Mar 16 06:48 schema 

  

tmp: 

total 4.0K 

4.0K drwx------ 2 kirti kirti 4.0K May  6 17:10 sra 

(base) kirti@kirti-Extensa-215-52:~/Desktop/project metabolite$ ls -shl * 

4.0K -rw-rw-r-- 1 kirti kirti 1.2K May  6 15:05 RNASeqpipelineOG.sh 

89M -rw-rw-r-- 1 kirti kirti  89M May  6 15:52 sratoolkit.3.2.1-ubuntu64.tar.gz 

4.0K -rw-rw-r-- 1 kirti kirti  110 May  6 15:30 SRR_Acc_List.txt 

  

data: 

total 21M 

21M -rw-rw-r-- 1 kirti kirti 21M May  6 16:20 SRR7621317_1.fastq 

  

script: 

total 4.0K 

4.0K -rw-rw-r-- 1 kirti kirti 227 May  6 17:32 RNAseqpipeline.sh 

  

sratoolkit.3.2.1-ubuntu64: 

total 72K 

4.0K drwxrwxr-x 3 kirti kirti 4.0K Mar 16 06:48 bin 

36K -rw-rw-r-- 1 kirti kirti  36K Mar 16 06:42 CHANGES 

4.0K drwxrwxr-x 3 kirti kirti 4.0K Mar 16 06:42 example 

4.0K -rw-rw-r-- 1 kirti kirti 1.7K Mar 16 06:42 README-blastn 

12K -rw-rw-r-- 1 kirti kirti  12K Mar 16 06:42 README.md 

8.0K -rw-rw-r-- 1 kirti kirti 4.9K Mar 16 06:42 README-vdb-config 

4.0K drwxrwxr-x 8 kirti kirti 4.0K Mar 16 06:48 schema 

  

tmp: 

total 4.0K 

4.0K drwx------ 2 kirti kirti 4.0K May  6 17:10 sra 

(base) kirti@kirti-Extensa-215-52:~/Desktop/project metabolite$ fastqc -h 

  

            FastQC - A high throughput sequence QC analysis tool 

  

SYNOPSIS 

  

fastqc seqfile1 seqfile2 .. seqfileN 

  

    fastqc [-o output dir] [--(no)extract] [-f fastq|bam|sam]  

           [-c contaminant file] seqfile1 .. seqfileN 

  

DESCRIPTION 

  

    FastQC reads a set of sequence files and produces from each one a quality 

    control report consisting of a number of different modules, each one of  

    which will help to identify a different potential type of problem in your 

    data. 

     

    If no files to process are specified on the command line then the program 

    will start as an interactive graphical application.  If files are provided 

    on the command line then the program will run with no user interaction 

    required.  In this mode it is suitable for inclusion into a standardised 

    analysis pipeline. 

     

    The options for the program as as follows: 

     

    -h --help       Print this help file and exit 

     

    -v --version    Print the version of the program and exit 

     

    -o --outdir     Create all output files in the specified output directory. 

                    Please note that this directory must exist as the program 

                    will not create it.  If this option is not set then the  

                    output file for each sequence file is created in the same 

                    directory as the sequence file which was processed. 

                     

    --casava        Files come from raw casava output. Files in the same sample 

                    group (differing only by the group number) will be analysed 

                    as a set rather than individually. Sequences with the filter 

                    flag set in the header will be excluded from the analysis. 

                    Files must have the same names given to them by casava 

                    (including being gzipped and ending with .gz) otherwise they 

                    won't be grouped together correctly. 

                     

    --nano          Files come from nanopore sequences and are in fast5 format. In 

                    this mode you can pass in directories to process and the program 

                    will take in all fast5 files within those directories and produce 

                    a single output file from the sequences found in all files.                     

                     

    --nofilter      If running with --casava then don't remove read flagged by 

                    casava as poor quality when performing the QC analysis. 

                    

    --extract       If set then the zipped output file will be uncompressed in 

                    the same directory after it has been created. If --delete is  

                    also specified then the zip file will be removed after the  

                    contents are unzipped.  

                     

    -j --java       Provides the full path to the java binary you want to use to 

                    launch fastqc. If not supplied then java is assumed to be in 

                    your path. 

                    

    --noextract     Do not uncompress the output file after creating it.  You 

                    should set this option if you do not wish to uncompress 

                    the output when running in non-interactive mode. 

                     

    --nogroup       Disable grouping of bases for reads >50bp. All reports will 

                    show data for every base in the read.  WARNING: Using this 

                    option will cause fastqc to crash and burn if you use it on 

                    really long reads, and your plots may end up a ridiculous size. 

                    You have been warned! 

                     

    --min_length    Sets an artificial lower limit on the length of the sequence 

                    to be shown in the report.  As long as you set this to a value 

                    greater or equal to your longest read length then this will be 

                    the sequence length used to create your read groups.  This can 

                    be useful for making directly comaparable statistics from  

                    datasets with somewhat variable read lengths. 

  

    --dup_length    Sets a length to which the sequences will be truncated when  

                    defining them to be duplicates, affecting the duplication and 

                    overrepresented sequences plot.  This can be useful if you have 

                    long reads with higher levels of miscalls, or contamination with 

                    adapter dimers containing UMI sequences. 

  

                     

    -f --format     Bypasses the normal sequence file format detection and 

                    forces the program to use the specified format.  Valid 

                    formats are bam,sam,bam_mapped,sam_mapped and fastq 

                     

  

    --memory        Sets the base amount of memory, in Megabytes, used to process  

                    each file.  Defaults to 512MB.  You may need to increase this if 

                    you have a file with very long sequences in it. 

                 

    --svg           Save the graphs in the report in SVG format. 

  

    -t --threads    Specifies the number of files which can be processed 

                    simultaneously.  Each thread will be allocated 250MB of 

                    memory so you shouldn't run more threads than your 

                    available memory will cope with, and not more than 

                    6 threads on a 32 bit machine 

                   

    -c              Specifies a non-default file which contains the list of 

    --contaminants  contaminants to screen overrepresented sequences against. 

                    The file must contain sets of named contaminants in the 

                    form name[tab]sequence.  Lines prefixed with a hash will 

                    be ignored. 

  

    -a              Specifies a non-default file which contains the list of 

    --adapters      adapter sequences which will be explicity searched against 

                    the library. The file must contain sets of named adapters 

                    in the form name[tab]sequence.  Lines prefixed with a hash 

                    will be ignored. 

                     

    -l              Specifies a non-default file which contains a set of criteria 

    --limits        which will be used to determine the warn/error limits for the 

                    various modules.  This file can also be used to selectively  

                    remove some modules from the output all together.  The format 

                    needs to mirror the default limits.txt file found in the 

                    Configuration folder. 

                     

   -k --kmers       Specifies the length of Kmer to look for in the Kmer content 

                    module. Specified Kmer length must be between 2 and 10. Default 

                    length is 7 if not specified. 

                     

   -q --quiet       Suppress all progress messages on stdout and only report errors. 

    

   -d --dir         Selects a directory to be used for temporary files written when 

                    generating report images. Defaults to system temp directory if 

                    not specified. 

                     

BUGS 

  

    Any bugs in fastqc should be reported either to simon.andrews@babraham.ac.uk 

    or in www.bioinformatics.babraham.ac.uk/bugzilla/ 

                    

     

(base) kirti@kirti-Extensa-215-52:~/Desktop/project metabolite$ ls 

data                 RNAseqpipeline.sh  sratoolkit.3.2.1-ubuntu64         SRR_Acc_List.txt 

RNASeqpipelineOG.sh  script             sratoolkit.3.2.1-ubuntu64.tar.gz  tmp 

(base) kirti@kirti-Extensa-215-52:~/Desktop/project metabolite$ cd script 

(base) kirti@kirti-Extensa-215-52:~/Desktop/project metabolite/script$ ls 

RNAseqpipeline.sh 

(base) kirti@kirti-Extensa-215-52:~/Desktop/project metabolite/script$ ./RNASeqpipeline.sh 

bash: ./RNASeqpipeline.sh: No such file or directory 

(base) kirti@kirti-Extensa-215-52:~/Desktop/project metabolite/script$ ./RNAseqpipeline.sh 

bash: ./RNAseqpipeline.sh: Permission denied 

(base) kirti@kirti-Extensa-215-52:~/Desktop/project metabolite/script$ chmod 755 RNAseqpipeline.sh 

(base) kirti@kirti-Extensa-215-52:~/Desktop/project metabolite/script$ ./RNAseqpipeline.sh 

./RNAseqpipeline.sh: line 6: cd: too many arguments 

Specified output directory 'data/' does not exist 

(base) kirti@kirti-Extensa-215-52:~/Desktop/project metabolite/script$ cd /home/kirti/Desktop/projectmeta 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta$ cd script 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/script$ ls 

RNAseqpipeline.sh 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/script$ chmod 755 RNAseqpipeline.sh 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/script$ ./RNAseqpipeline.sh 

./RNAseqpipeline.sh: line 6: cd: too many arguments 

Specified output directory 'data/' does not exist 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/script$ ./RNAseqpipeline.sh 

./RNAseqpipeline.sh: line 6: cd: too many arguments 

Specified output directory 'data/' does not exist 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/script$ cd 

(base) kirti@kirti-Extensa-215-52:~$ cd /home/kirti/Desktop/projectmeta 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta$ ls 

data  script  sra 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta$ ls -shl * 

data: 

total 21M 

21M -rw-rw-r-- 1 kirti kirti 21M May  6 16:20 SRR7621317_1.fastq 

  

script: 

total 4.0K 

4.0K -rwxr-xr-x 1 kirti kirti 180 May  6 21:25 RNAseqpipeline.sh 

  

sra: 

total 89M 

4.0K -rw-rw-r-- 1 kirti kirti 1.2K May  6 15:05 RNASeqpipelineOG.sh 

4.0K drwxrwxr-x 5 kirti kirti 4.0K Mar 16 06:48 sratoolkit.3.2.1-ubuntu64 

89M -rw-rw-r-- 1 kirti kirti  89M May  6 15:52 sratoolkit.3.2.1-ubuntu64.tar.gz 

4.0K -rw-rw-r-- 1 kirti kirti  110 May  6 15:30 SRR_Acc_List.txt 

4.0K drwxrwxr-x 3 kirti kirti 4.0K May  6 16:20 tmp 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta$ cd script 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/script$ ls 

RNAseqpipeline.sh 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/script$ ./RNAseqpipeline.sh 

null 

Started analysis of SRR7621317_1.fastq 

Approx 5% complete for SRR7621317_1.fastq 

Approx 10% complete for SRR7621317_1.fastq 

Approx 15% complete for SRR7621317_1.fastq 

Approx 20% complete for SRR7621317_1.fastq 

Approx 25% complete for SRR7621317_1.fastq 

Approx 30% complete for SRR7621317_1.fastq 

Approx 35% complete for SRR7621317_1.fastq 

Approx 40% complete for SRR7621317_1.fastq 

Approx 45% complete for SRR7621317_1.fastq 

Approx 50% complete for SRR7621317_1.fastq 

Approx 55% complete for SRR7621317_1.fastq 

Approx 60% complete for SRR7621317_1.fastq 

Approx 65% complete for SRR7621317_1.fastq 

Approx 70% complete for SRR7621317_1.fastq 

Approx 75% complete for SRR7621317_1.fastq 

Approx 80% complete for SRR7621317_1.fastq 

Approx 85% complete for SRR7621317_1.fastq 

Approx 90% complete for SRR7621317_1.fastq 

Approx 95% complete for SRR7621317_1.fastq 

Analysis complete for SRR7621317_1.fastq 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/script$ ./RNAseqpipeline.sh 

Skipping 'data/SRR7621317_1.fastq' which didn't exist, or couldn't be read 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/script$ ./RNAseqpipeline.sh 

null 

Started analysis of SRR7621326_1.fastq 

Approx 5% complete for SRR7621326_1.fastq 

Approx 10% complete for SRR7621326_1.fastq 

Approx 15% complete for SRR7621326_1.fastq 

Approx 20% complete for SRR7621326_1.fastq 

Approx 25% complete for SRR7621326_1.fastq 

Approx 30% complete for SRR7621326_1.fastq 

Approx 35% complete for SRR7621326_1.fastq 

Approx 40% complete for SRR7621326_1.fastq 

Approx 45% complete for SRR7621326_1.fastq 

Approx 50% complete for SRR7621326_1.fastq 

Approx 55% complete for SRR7621326_1.fastq 

Approx 60% complete for SRR7621326_1.fastq 

Approx 65% complete for SRR7621326_1.fastq 

Approx 70% complete for SRR7621326_1.fastq 

Approx 75% complete for SRR7621326_1.fastq 

Approx 80% complete for SRR7621326_1.fastq 

Approx 85% complete for SRR7621326_1.fastq 

Approx 90% complete for SRR7621326_1.fastq 

Approx 95% complete for SRR7621326_1.fastq 

Analysis complete for SRR7621326_1.fastq 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/script$ ./RNAseqpipeline.sh 

+ SECONDS=0 

+ cd /home/kirti/Desktop/projectmeta/ 

+ fastqc data/SRR7621326_1.fastq -o data/ 

null 

Started analysis of SRR7621326_1.fastq 

Approx 5% complete for SRR7621326_1.fastq 

Approx 10% complete for SRR7621326_1.fastq 

Approx 15% complete for SRR7621326_1.fastq 

Approx 20% complete for SRR7621326_1.fastq 

Approx 25% complete for SRR7621326_1.fastq 

Approx 30% complete for SRR7621326_1.fastq 

Approx 35% complete for SRR7621326_1.fastq 

Approx 40% complete for SRR7621326_1.fastq 

Approx 45% complete for SRR7621326_1.fastq 

Approx 50% complete for SRR7621326_1.fastq 

Approx 55% complete for SRR7621326_1.fastq 

Approx 60% complete for SRR7621326_1.fastq 

Approx 65% complete for SRR7621326_1.fastq 

Approx 70% complete for SRR7621326_1.fastq 

Approx 75% complete for SRR7621326_1.fastq 

Approx 80% complete for SRR7621326_1.fastq 

Approx 85% complete for SRR7621326_1.fastq 

Approx 90% complete for SRR7621326_1.fastq 

Approx 95% complete for SRR7621326_1.fastq 

Analysis complete for SRR7621326_1.fastq 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/script$ cd data 

bash: cd: data: No such file or directory 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/script$ cd ..data/ 

bash: cd: ..data/: No such file or directory 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/script$ cd /home/kirti/Desktop/projectmeta/data 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/data$ ls 

SRR7621326_1.fastq  SRR7621326_1_fastqc.html  SRR7621326_1_fastqc.zip 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/data$ cd script 

bash: cd: script: No such file or directory 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/data$ cd /home/kirti/Desktop/projectmeta/script 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/script$ ls 

RNAseqpipeline.sh 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/script$ ./RNAseqpipeline.sh  

null 

Started analysis of SRR7621326_1.fastq 

Approx 5% complete for SRR7621326_1.fastq 

Approx 10% complete for SRR7621326_1.fastq 

Approx 15% complete for SRR7621326_1.fastq 

Approx 20% complete for SRR7621326_1.fastq 

Approx 25% complete for SRR7621326_1.fastq 

Approx 30% complete for SRR7621326_1.fastq 

Approx 35% complete for SRR7621326_1.fastq 

Approx 40% complete for SRR7621326_1.fastq 

Approx 45% complete for SRR7621326_1.fastq 

Approx 50% complete for SRR7621326_1.fastq 

Approx 55% complete for SRR7621326_1.fastq 

Approx 60% complete for SRR7621326_1.fastq 

Approx 65% complete for SRR7621326_1.fastq 

Approx 70% complete for SRR7621326_1.fastq 

Approx 75% complete for SRR7621326_1.fastq 

Approx 80% complete for SRR7621326_1.fastq 

Approx 85% complete for SRR7621326_1.fastq 

Approx 90% complete for SRR7621326_1.fastq 

Approx 95% complete for SRR7621326_1.fastq 

Analysis complete for SRR7621326_1.fastq 

Error: Unable to access jarfile /home/kirti/home/kirti/Desktop/projectmeta/Trimmomatic-0.39/Trimmomatic-0.39.zip 

Trimmomatic finished running! 

Skipping 'data/demo_trimmed.fastq' which didn't exist, or couldn't be read 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/script$ ./RNAseqpipeline.sh  

null 

Started analysis of SRR7621326_1.fastq 

Approx 5% complete for SRR7621326_1.fastq 

Approx 10% complete for SRR7621326_1.fastq 

Approx 15% complete for SRR7621326_1.fastq 

Approx 20% complete for SRR7621326_1.fastq 

Approx 25% complete for SRR7621326_1.fastq 

Approx 30% complete for SRR7621326_1.fastq 

Approx 35% complete for SRR7621326_1.fastq 

Approx 40% complete for SRR7621326_1.fastq 

Approx 45% complete for SRR7621326_1.fastq 

Approx 50% complete for SRR7621326_1.fastq 

Approx 55% complete for SRR7621326_1.fastq 

Approx 60% complete for SRR7621326_1.fastq 

Approx 65% complete for SRR7621326_1.fastq 

Approx 70% complete for SRR7621326_1.fastq 

Approx 75% complete for SRR7621326_1.fastq 

Approx 80% complete for SRR7621326_1.fastq 

Approx 85% complete for SRR7621326_1.fastq 

Approx 90% complete for SRR7621326_1.fastq 

Approx 95% complete for SRR7621326_1.fastq 

Analysis complete for SRR7621326_1.fastq 

Error: Unable to access jarfile /home/kirti/home/kirti/Desktop/projectmeta/Trimmomatic-0.39/Trimmomatic-0.39/trimmomatic-0.39.jar 

Trimmomatic finished running! 

Skipping 'data/demo_trimmed.fastq' which didn't exist, or couldn't be read 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/script$ ./RNAseqpipeline.sh  

null 

Started analysis of SRR7621326_1.fastq 

Approx 5% complete for SRR7621326_1.fastq 

Approx 10% complete for SRR7621326_1.fastq 

Approx 15% complete for SRR7621326_1.fastq 

Approx 20% complete for SRR7621326_1.fastq 

Approx 25% complete for SRR7621326_1.fastq 

Approx 30% complete for SRR7621326_1.fastq 

Approx 35% complete for SRR7621326_1.fastq 

Approx 40% complete for SRR7621326_1.fastq 

Approx 45% complete for SRR7621326_1.fastq 

Approx 50% complete for SRR7621326_1.fastq 

Approx 55% complete for SRR7621326_1.fastq 

Approx 60% complete for SRR7621326_1.fastq 

Approx 65% complete for SRR7621326_1.fastq 

Approx 70% complete for SRR7621326_1.fastq 

Approx 75% complete for SRR7621326_1.fastq 

Approx 80% complete for SRR7621326_1.fastq 

Approx 85% complete for SRR7621326_1.fastq 

Approx 90% complete for SRR7621326_1.fastq 

Approx 95% complete for SRR7621326_1.fastq 

Analysis complete for SRR7621326_1.fastq 

Error: Unable to access jarfile /home/kirti/home/kirti/Desktop/projectmeta/Trimmomatic/Trimmomatic-0.39/trimmomatic-0.39 

Trimmomatic finished running! 

Skipping 'data/demo_trimmed.fastq' which didn't exist, or couldn't be read 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/script$ ./RNAseqpipeline.sh  

Error: Unable to access jarfile /home/kirti/home/kirti/Desktop/projectmeta/Trimmomatic-0.39/trimmomatic-0.39.jar 

Trimmomatic finished running! 

Skipping 'data/demo_trimmed.fastq' which didn't exist, or couldn't be read 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/script$ ./RNAseqpipeline.sh  

Error: Unable to access jarfile /home/kirti/home/kirti/Desktop/projectmeta/Trimmomatic-0.39/trimmomatic-0.39.jar 

Trimmomatic finished running! 

Skipping 'data/demo_trimmed.fastq' which didn't exist, or couldn't be read 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/script$ ./RNAseqpipeline.sh  

Error: Unable to access jarfile /home/kirti/home/kirti/Desktop/projectmeta/Trimmomatic-0.39/trimmomatic-0.39 

Trimmomatic finished running! 

Skipping 'data/demo_trimmed.fastq' which didn't exist, or couldn't be read 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/script$ ./RNAseqpipeline.sh  

Error: Unable to access jarfile /home/kirti/home/kirti/Desktop/projectmeta/Trimmomatic-0.39/trimmomatic-0.39 

Trimmomatic finished running! 

Skipping 'data/demo_trimmed.fastq' which didn't exist, or couldn't be read 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/script$ ./RNAseqpipeline.sh  

TrimmomaticSE: Started with arguments: 

-threads 4 -phred33 data/SRR7621326_1.fastq data/SRR7621326_1_trimmed.fastq TRAILING:10 

Input Reads: 539513 Surviving: 539501 (100.00%) Dropped: 12 (0.00%) 

TrimmomaticSE: Completed successfully 

Trimmomatic finished running! 

Skipping 'data/demo_trimmed.fastq' which didn't exist, or couldn't be read 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/script$ ./RNAseqpipeline.sh  

TrimmomaticSE: Started with arguments: 

-threads 4 -phred33 data/SRR7621326_1.fastq data/SRR7621326_1_trimmed.fastq TRAILING:10 

Input Reads: 539513 Surviving: 539501 (100.00%) Dropped: 12 (0.00%) 

TrimmomaticSE: Completed successfully 

Trimmomatic finished running! 

null 

Started analysis of SRR7621326_1_trimmed.fastq 

Approx 5% complete for SRR7621326_1_trimmed.fastq 

Approx 10% complete for SRR7621326_1_trimmed.fastq 

Approx 15% complete for SRR7621326_1_trimmed.fastq 

Approx 20% complete for SRR7621326_1_trimmed.fastq 

Approx 25% complete for SRR7621326_1_trimmed.fastq 

Approx 30% complete for SRR7621326_1_trimmed.fastq 

Approx 35% complete for SRR7621326_1_trimmed.fastq 

Approx 40% complete for SRR7621326_1_trimmed.fastq 

Approx 45% complete for SRR7621326_1_trimmed.fastq 

Approx 50% complete for SRR7621326_1_trimmed.fastq 

Approx 55% complete for SRR7621326_1_trimmed.fastq 

Approx 60% complete for SRR7621326_1_trimmed.fastq 

Approx 65% complete for SRR7621326_1_trimmed.fastq 

Approx 70% complete for SRR7621326_1_trimmed.fastq 

Approx 75% complete for SRR7621326_1_trimmed.fastq 

Approx 80% complete for SRR7621326_1_trimmed.fastq 

Approx 85% complete for SRR7621326_1_trimmed.fastq 

Approx 90% complete for SRR7621326_1_trimmed.fastq 

Approx 95% complete for SRR7621326_1_trimmed.fastq 

Analysis complete for SRR7621326_1_trimmed.fastq 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/script$ cd /home/kirti/Desktop/projectmeta/hisat2-2.2.1 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/hisat2-2.2.1$ cd /home/kirti/Desktop/projectmeta/hisat2-2.2.1/grch38 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/hisat2-2.2.1/grch38$ ls 

genome.1.ht2  genome.3.ht2  genome.5.ht2  genome.7.ht2  make_grch38.sh 

genome.2.ht2  genome.4.ht2  genome.6.ht2  genome.8.ht2 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/hisat2-2.2.1/grch38$ cd script 

bash: cd: script: No such file or directory 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/hisat2-2.2.1/grch38$ cd 

(base) kirti@kirti-Extensa-215-52:~$ cd /home/kirti/Desktop/projectmeta/script 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/script$ ./RNAseqpipeline.sh  

539501 reads; of these: 

  539501 (100.00%) were unpaired; of these: 

    169943 (31.50%) aligned 0 times 

    351980 (65.24%) aligned exactly 1 time 

    17578 (3.26%) aligned >1 times 

68.50% overall alignment rate 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/script$ cd /home/kirti/Desktop/projectmeta/hisat2-2.2.1 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/hisat2-2.2.1$ ls 

AUTHORS                  hisat2-build-l-debug                    hisat2-repeat 

demo_trimmed.bam         hisat2-build-s                          hisat2-repeat-debug 

example                  hisat2-build-s-debug                    hisat2_simulate_reads.py 

extract_exons.py         hisat2_extract_exons.py                 Homo_sapiens.GRCh38.113.gtf 

extract_splice_sites.py  hisat2_extract_snps_haplotypes_UCSC.py  Homo_sapiens.GRCh38.113.gtf.gz 

grch38                   hisat2_extract_snps_haplotypes_VCF.py   LICENSE 

hisat2                   hisat2_extract_splice_sites.py          MANUAL 

hisat2-align-l           hisat2-inspect                          MANUAL.markdown 

hisat2-align-l-debug     hisat2-inspect-l                        NEWS 

hisat2-align-s           hisat2-inspect-l-debug                  scripts 

hisat2-align-s-debug     hisat2-inspect-s                        SRR7621326_1_trimmed.bam 

hisat2-build             hisat2-inspect-s-debug                  TUTORIAL 

hisat2-build-l           hisat2_read_statistics.py               VERSION 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/hisat2-2.2.1$ samtools view -h SRR7621326_1_trimmed.bam | less     ####HERE YOU STUCK HOW TO EXIT JUST CLICK q TO EXIT 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/hisat2-2.2.1$  

 (base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/hisat2-2.2.1$ cd 

(base) kirti@kirti-Extensa-215-52:~$ cd /home/kirti/Desktop/projectmeta 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta$ wget ftp://ftp.ensembl.org/pub/release-114/gtf/homo_sapiens/Homo_sapiens.GRCh38.114.gtf.gz 

--2025-05-07 16:23:10--  ftp://ftp.ensembl.org/pub/release-114/gtf/homo_sapiens/Homo_sapiens.GRCh38.114.gtf.gz 

           => ‘Homo_sapiens.GRCh38.114.gtf.gz’ 

Resolving ftp.ensembl.org (ftp.ensembl.org)... 193.62.193.169 

Connecting to ftp.ensembl.org (ftp.ensembl.org)|193.62.193.169|:21... connected. 

Logging in as anonymous ... Logged in! 

==> SYST ... done.    ==> PWD ... done. 

==> TYPE I ... done.  ==> CWD (1) /pub/release-114/gtf/homo_sapiens ...  

No such directory ‘pub/release-114/gtf/homo_sapiens’. 

  

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta$ wget https://ftp.ensembl.org/pub/current_gtf/homo_sapiens/Homo_sapiens.GRCh38.110.gtf.gz 

--2025-05-07 16:28:45--  https://ftp.ensembl.org/pub/current_gtf/homo_sapiens/Homo_sapiens.GRCh38.110.gtf.gz 

Resolving ftp.ensembl.org (ftp.ensembl.org)... 193.62.193.169 

Connecting to ftp.ensembl.org (ftp.ensembl.org)|193.62.193.169|:443... connected. 

HTTP request sent, awaiting response... 404 Not Found 

2025-05-07 16:28:47 ERROR 404: Not Found. 

  

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta$ wget https://ftp.ensembl.org/pub/current_gtf/homo_sapiens/Homo_sapiens.GRCh38.113.gtf.gz 

--2025-05-07 16:34:46--  https://ftp.ensembl.org/pub/current_gtf/homo_sapiens/Homo_sapiens.GRCh38.113.gtf.gz 

Resolving ftp.ensembl.org (ftp.ensembl.org)... 193.62.193.169 

Connecting to ftp.ensembl.org (ftp.ensembl.org)|193.62.193.169|:443... connected. 

HTTP request sent, awaiting response... 200 OK 

Length: 64141785 (61M) [application/x-gzip] 

Saving to: ‘Homo_sapiens.GRCh38.113.gtf.gz’ 

  

Homo_sapiens.GRCh38.113.gtf.  17%[=======>                                       ]  10.61M   205KB/s    in 2m 49s   

  

2025-05-07 16:38:12 (64.4 KB/s) - Connection closed at byte 11127691. Retrying. 

  

--2025-05-07 16:38:13--  (try: 2)  https://ftp.ensembl.org/pub/current_gtf/homo_sapiens/Homo_sapiens.GRCh38.113.gtf.gz 

Connecting to ftp.ensembl.org (ftp.ensembl.org)|193.62.193.169|:443... connected. 

HTTP request sent, awaiting response... 206 Partial Content 

Length: 64141785 (61M), 53014094 (51M) remaining [application/x-gzip] 

Saving to: ‘Homo_sapiens.GRCh38.113.gtf.gz’ 

  

Homo_sapiens.GRCh38.113.gtf. 100%[++++++++======================================>]  61.17M   761KB/s    in 1m 55s   

  

2025-05-07 16:40:09 (450 KB/s) - ‘Homo_sapiens.GRCh38.113.gtf.gz’ saved [64141785/64141785] 

  

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta$ cd  

(base) kirti@kirti-Extensa-215-52:~$ cd /home/kirti/Desktop/projectmeta/script 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/script$ ./RNAseqpipeline.sh  

The "-S" option has been depreciated. 

  

        ==========     _____ _    _ ____  _____  ______          _____   

        =====         / ____| |  | |  _ \|  __ \|  ____|   /\   |  __ \  

          =====      | (___ | |  | | |_) | |__) | |__     /  \  | |  | | 

            ====      \___ \| |  | |  _ <|  _  /|  __|   / /\ \ | |  | | 

              ====    ____) | |__| | |_) | | \ \| |____ / ____ \| |__| | 

        ==========   |_____/ \____/|____/|_|  \_\______/_/    \_\_____/ 

  v2.0.6 

  

//========================== featureCounts setting ===========================\\ 

||                                                                            || 

||             Input files : 1 BAM file                                       || 

||                                                                            || 

||                           demo_trimmed.bam                                 || 

||                                                                            || 

||             Output file : SRR7621326_1_featurecounts.txt                   || 

||                 Summary : SRR7621326_1_featurecounts.txt.summary           || 

||              Paired-end : no                                               || 

||        Count read pairs : no                                               || 

||              Annotation : Homo_sapiens.GRCh38.113.gtf (GTF)                || 

||      Dir for temp files : quants                                           || 

||                                                                            || 

||                 Threads : 1                                                || 

||                   Level : meta-feature level                               || 

||      Multimapping reads : not counted                                      || 

|| Multi-overlapping reads : not counted                                      || 

||   Min overlapping bases : 1                                                || 

||                                                                            || 

\\============================================================================// 

  

//================================= Running ==================================\\ 

||                                                                            || 

|| Load annotation file Homo_sapiens.GRCh38.113.gtf ...                       || 

||    Features : 2164410                                                      || 

||    Meta-features : 78932                                                   || 

||    Chromosomes/contigs : 70                                                || 

||                                                                            || 

|| Process BAM file demo_trimmed.bam...                                       || 

||    Single-end reads are included.                                          || 

||    Total alignments : 1430243                                              || 

||    Successfully assigned alignments : 865176 (60.5%)                       || 

||    Running time : 0.03 minutes                                             || 

||                                                                            || 

|| Write the final count table.                                               || 

|| Write the read assignment summary.                                         || 

||                                                                            || 

|| Summary of counting results can be found in file "quants/SRR7621326_1_fea  || 

|| turecounts.txt.summary"                                                    || 

||                                                                            || 

\\============================================================================// 

  

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/script$ cd /home/kirti/Desktop/projectmeta/quants 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/quants$ ls 

SRR7621326_1_featurecounts.txt  SRR7621326_1_featurecounts.txt.summary 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/quants$  

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/quants$  

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/quants$  

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/quants$  

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/quants$  

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/quants$  

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/quants$ cat SRR7621326_1_featurecounts.txt 

# Program:featureCounts v2.0.6; Command:"featureCounts" "-S" "2" "-a" "/home/kirti/Desktop/projectmeta/Homo_sapiens.GRCh38.113.gtf" "-o" "quants/SRR7621326_1_featurecounts.txt" "/home/kirti/Desktop/projectmeta/hisat2-2.2.1/demo_trimmed.bam"  

Geneid Chr Start End Strand Length /home/kirti/Desktop/projectmeta/hisat2-2.2.1/demo_trimmed.bam 

GIVE THE LENGTH OF THE FILE  

 

AND IT GIVE THE SUMMARY OF THE DATA BAM FILE  

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/quants$ cat SRR7621326_1_featurecounts.txt.summary 

Status /home/kirti/Desktop/projectmeta/hisat2-2.2.1/demo_trimmed.bam 

Assigned 865176 

Unassigned_Unmapped 86563 

Unassigned_Read_Type 0 

Unassigned_Singleton 0 

Unassigned_MappingQuality 0 

Unassigned_Chimera 0 

Unassigned_FragmentLength 0 

Unassigned_Duplicate 0 

Unassigned_MultiMapping 261300 

Unassigned_Secondary 0 

Unassigned_NonSplit 0 

Unassigned_NoFeatures 113211 

Unassigned_Overlapping_Length 0 

Unassigned_Ambiguity 103993 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/quants$ cat SRR7621326_1_featurecounts.txt | less 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/quants$ cat SRR7621326_1_featurecounts.txt | less 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/quants$ cat SRR7621326_1_featurecounts.txt | cut -f1.7 | less 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/quants$ cat SRR7621326_1_featurecounts.txt | cut -f1.7 | less 

cut: invalid field value ‘.7’ 

Try 'cut --help' for more information. 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/quants$ cat SRR7621326_1_featurecounts.txt | less 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/quants$ cat SRR7621326_1_featurecounts.txt | cut -f1.7 | less 

cut: invalid field value ‘.7’ 

Try 'cut --help' for more information. 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/quants$ cat SRR7621326_1_featurecounts.txt | cut -f1,7 | less 

IT GIVE US HEADING  

 

 

RUN WHOLE PIPELINE ONE AFTER COMMENT OUT YOUR WHOLE CODE 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/script$ ./RNAseqpipeline.sh 

null 

Started analysis of SRR7621326_1.fastq 

Approx 5% complete for SRR7621326_1.fastq 

Approx 10% complete for SRR7621326_1.fastq 

Approx 15% complete for SRR7621326_1.fastq 

Approx 20% complete for SRR7621326_1.fastq 

Approx 25% complete for SRR7621326_1.fastq 

Approx 30% complete for SRR7621326_1.fastq 

Approx 35% complete for SRR7621326_1.fastq 

Approx 40% complete for SRR7621326_1.fastq 

Approx 45% complete for SRR7621326_1.fastq 

Approx 50% complete for SRR7621326_1.fastq 

Approx 55% complete for SRR7621326_1.fastq 

Approx 60% complete for SRR7621326_1.fastq 

Approx 65% complete for SRR7621326_1.fastq 

Approx 70% complete for SRR7621326_1.fastq 

Approx 75% complete for SRR7621326_1.fastq 

Approx 80% complete for SRR7621326_1.fastq 

Approx 85% complete for SRR7621326_1.fastq 

Approx 90% complete for SRR7621326_1.fastq 

Approx 95% complete for SRR7621326_1.fastq 

Analysis complete for SRR7621326_1.fastq 

TrimmomaticSE: Started with arguments: 

-threads 4 -phred33 data/SRR7621326_1.fastq data/SRR7621326_1_trimmed.fastq TRAILING:10 

Input Reads: 539513 Surviving: 539501 (100.00%) Dropped: 12 (0.00%) 

TrimmomaticSE: Completed successfully 

TRIMMOMATIC FINISHED RUNNING ! 

null 

Started analysis of SRR7621326_1_trimmed.fastq 

Approx 5% complete for SRR7621326_1_trimmed.fastq 

Approx 10% complete for SRR7621326_1_trimmed.fastq 

Approx 15% complete for SRR7621326_1_trimmed.fastq 

Approx 20% complete for SRR7621326_1_trimmed.fastq 

Approx 25% complete for SRR7621326_1_trimmed.fastq 

Approx 30% complete for SRR7621326_1_trimmed.fastq 

Approx 35% complete for SRR7621326_1_trimmed.fastq 

Approx 40% complete for SRR7621326_1_trimmed.fastq 

Approx 45% complete for SRR7621326_1_trimmed.fastq 

Approx 50% complete for SRR7621326_1_trimmed.fastq 

Approx 55% complete for SRR7621326_1_trimmed.fastq 

Approx 60% complete for SRR7621326_1_trimmed.fastq 

Approx 65% complete for SRR7621326_1_trimmed.fastq 

Approx 70% complete for SRR7621326_1_trimmed.fastq 

Approx 75% complete for SRR7621326_1_trimmed.fastq 

Approx 80% complete for SRR7621326_1_trimmed.fastq 

Approx 85% complete for SRR7621326_1_trimmed.fastq 

Approx 90% complete for SRR7621326_1_trimmed.fastq 

Approx 95% complete for SRR7621326_1_trimmed.fastq 

Analysis complete for SRR7621326_1_trimmed.fastq 

539501 reads; of these: 

  539501 (100.00%) were unpaired; of these: 

    169943 (31.50%) aligned 0 times 

    351980 (65.24%) aligned exactly 1 time 

    17578 (3.26%) aligned >1 times 

68.50% overall alignment rate 

HISAT2 FINISHED RUNNING ! 

The "-S" option has been depreciated. 

  

        ==========     _____ _    _ ____  _____  ______          _____   

        =====         / ____| |  | |  _ \|  __ \|  ____|   /\   |  __ \  

          =====      | (___ | |  | | |_) | |__) | |__     /  \  | |  | | 

            ====      \___ \| |  | |  _ <|  _  /|  __|   / /\ \ | |  | | 

              ====    ____) | |__| | |_) | | \ \| |____ / ____ \| |__| | 

        ==========   |_____/ \____/|____/|_|  \_\______/_/    \_\_____/ 

  v2.0.6 

  

//========================== featureCounts setting ===========================\\ 

||                                                                            || 

||             Input files : 1 BAM file                                       || 

||                                                                            || 

||                           demo_trimmed.bam                                 || 

||                                                                            || 

||             Output file : SRR7621326_1_featurecounts.txt                   || 

||                 Summary : SRR7621326_1_featurecounts.txt.summary           || 

||              Paired-end : no                                               || 

||        Count read pairs : no                                               || 

||              Annotation : Homo_sapiens.GRCh38.113.gtf (GTF)                || 

||      Dir for temp files : quants                                           || 

||                                                                            || 

||                 Threads : 1                                                || 

||                   Level : meta-feature level                               || 

||      Multimapping reads : not counted                                      || 

|| Multi-overlapping reads : not counted                                      || 

||   Min overlapping bases : 1                                                || 

||                                                                            || 

\\============================================================================// 

  

//================================= Running ==================================\\ 

||                                                                            || 

|| Load annotation file Homo_sapiens.GRCh38.113.gtf ...                       || 

||    Features : 2164410                                                      || 

||    Meta-features : 78932                                                   || 

||    Chromosomes/contigs : 70                                                || 

||                                                                            || 

|| Process BAM file demo_trimmed.bam...                                       || 

||    Single-end reads are included.                                          || 

||    Total alignments : 1430243                                              || 

||    Successfully assigned alignments : 865176 (60.5%)                       || 

||    Running time : 0.03 minutes                                             || 

||                                                                            || 

|| Write the final count table.                                               || 

|| Write the read assignment summary.                                         || 

||                                                                            || 

|| Summary of counting results can be found in file "quants/SRR7621326_1_fea  || 

|| turecounts.txt.summary"                                                    || 

||                                                                            || 

\\============================================================================// 

  

FEATURECOUNT FINISHED RUNNING ! 

1 minutes and 3 seconds elapsed. 

(base) kirti@kirti-Extensa-215-52:~/Desktop/projectmeta/script$  

 

This whole process give the count data and the we can us this in DESeq2 using salmon ------Salmon is a free (both as in “free beer” and “free speech”) software tool for estimating transcript-level abundance from RNA-seq read data.  