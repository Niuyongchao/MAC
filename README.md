# MAC
Merging assemblies by using adjacency algebraic model and classification

## Pre-installed:

PHP: http://www.php.net/

MUMmer: http://mummer.sourceforge.net/ 

Please make sure the path of MUMmer has been added into system variable.

## Usage: 

php MAC.php <contig_1.fasta> <contig_2.fasta> ... <paired_reads1.fastq> <paired_reads2.fastq> <read_length> <insert_size> <output_path> <other_options>


## Option:
	
<contigs.fasta>	Contig files generated by different assembly methods. At least two contig files are needed, please separate each file with space

<paired_reads1.fastq>	The left end of Paired-end/mate-pair reads file

<paired_reads2.fastq>	The right end of Paired-end/mate-pair reads file

<read_length>	The average length of paired reads

<insert_size>	The insert size of paired reads

<output_path>	The path to store the result files

-h      Show help message 

-e      Use evaluation

-r 		Retain all the short contigs 

## Notification:
- The output merged assembly file will be named "MixOut.fasta", which saved under your output path.
- MAC dosen't develop in parallel running, if you have too many contig files or the files are larger than 200M, we recommend running two contig files each time, then merge these result files.
- The old version of MAC retained all the short contigs in result file, which would cause high redundancy. In the updated version of MAC, the short contigs are removed by default. If you want to retain these contigs, please set "-r" option.

## Demo:

Here we provide a demo for testing the performance of MAC, users can run the commandline:

```
php MAC.php soap_ctg.fa abyss_ctg.fa velvet_ctg.fa paired-reads_1.fastq paired-reads_2.fastq 250 600 /path_of_output/out_name
```

Since short contigs are removed by default, if you want to retain as many contigs as possible, add "-r" in the commandline:

```
php MAC.php soap_ctg.fa abyss_ctg.fa velvet_ctg.fa paired-reads_1.fastq paired-reads_2.fastq 250 600 /path_of_output/out_name -r
```
