Introduction
The readme from Pipeline.scm.
Pipeline.scm is a scheme file.
The pipeline is used to calculate specificity for a histone mark on tissues.
After the user delivers the input for the script, the pipeline needs to be ran on a linux
To start  GNU Guix and the GWL extension are needed.
GNU Guix:
https://www.gnu.org/software/guix/manual/html_node/Binary-Installation.html
GWL extension:
https://www.guixwl.org/getting-started

Make a path: export GUIX_WORKFLOW_PATH="/Path/to/scripts/"
The pipeline is used to calculate specificity for a histone mark on tissues.

Needed for the pipeline: 
The parameters need to be changed inside the script.
The parameters can be found at the start of the script.
1. REF= A indexed reference genome file 
2. Genome= A genome file, only if the input files are .sra
3. ControlString= The part of a the controle file names that is unique for control files
4. Directory= The Directory containing all the files 
5. Output_Directory= A output Directory where all output can be stored, should differ from Directory but doesn't have to exist
6. dir1000G= Directory with beagle files
7. BeaglePopList= (tab delimited) file listing individuals present in the Beagle files along with population information (popName) in the third column
8. popName= The origin of the population
9. SNPmappings= (tab delimited) SNP name, chromosome (chrN format), base pair position. These are the SNPs with location (location needs to be the same as in BeaglePopList)
10. LDwindow= a window to compute LD between the index SNP and SNPs 
11. r2= cut­off for Ld calculation
12. histoneName= Name of the histonemark
13. permutations= How many times does a permutation needs to be done.
 
14. bgDir= Background(can be downloaded from http://archive.broadinstitute.org/mpg/epigwas/)
IMPORTANT: tissue indexing must be the same for background and phenotype SNPs.    

To run the pipeline:

UMC:  guixr workflow -r Pipeline-workflow -e grid-engine
General: guix workflow -r Pipeline-workflow -e <server name>