MiSeqPipeline Version 1.0 05/11/2016


GENERAL USAGE NOTES
-------------------
This shell script implements a pipeline for Illumina MiSeq Sequencing for 
samples that takes BAM input from CLCbio, sorts BAM file, index BAM files, 
uses mpileup for sorted BAM files, filters high quality SNPs, and converts 
into FASTA file for exporting back to the CLCbio for generating tree.

Usage: MiSeqPipeline [-d] --inputBamDir=/path/to/inputBamDir \
		--refGenomeFileName=nameOfReferenceGenomeFile \ 
		[--SAM_HOME=/path/to/SAMTools]

All the parameters within [] are optional.

-d			to run the program in debug mode
--inputBamDir		directory where the input BAM files are located
--refGenomeFileName	Name of the Reference genome file located in 
			the input BAM directory
--SAM_HOME		directory where SAM tools is located.  By default,
			this is /usr/local/bin

This program should be run from the directory where the MiSeqPipeline
shell script is located.  If current directory is not in your PATH,
you may need to use ./MiSeqPipeline.

The program creates a log file with the time stamp of the run time
in the directory in the sorted_bam directory the inputBamDir folder.
Whatever is shown on the screen while the script is running is also 
captured in the log file.  If the program is run in debug mode, more
logging information is captured.


INSTALLING ON MAC OS X
-----------------------
This shell script uses SAMTools, vcfutils, BCFTools, VCFTools, vcf-tab-to-fasta
utilities.  Please make sure that these packages are present on the computer 
before this shell script is installed.

To install this shell script, simply copy this script to a folder that you have
created for this program.

$ cd /path/to/installation/directory
$ cp /path/to/MiSeqPipeline .
$ chmod u+x ./MiSeqPipeline 
$ export PATH=$PATH:/path/to/installation/directory

We made the shell script executable and added the current directory to the PATH variable.

Contact
-------
Rituparna Mukhopadhyay
Email: rituparna.mukhopadhyay@cdph.ca.gov


Copyright 2016 California Departmnet of Public Health (MDL)
