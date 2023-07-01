# LTS-analysis

## 0. About LTS-analysis

We introduce a new analysis based on local topological similarity (LTS): some components maintained their pair-ratios in two microbial communities, even if their relative abundance changes sharply. LTS analysis is tolerant to amount of input DNA, presence of contaminants and stochastic disturbance, requires no delicate parameter choice, simplifies data integration and interpretation, unravels pathology for both infectious and non-infectious diseases, and is compatible on both metagenomic and 16s rRNA datasets. 


## 1. Installation

####	System requirements

1. 64-bit computer
2. 1 GB disk space or higher
3. 64 GB Mem or higher
4. Linux (CentOS Linux release 7.4.1708)

####	Required dependencies

1. R (>=4.2.3)
2. R packages "data.table","magrittr" and "optparse"
3. Python (XXXX)
4. XXXX

####	Installing

1. Download the codes from [codes](https://github.com/HuLong-BI/LTS-analysis/tree/master/codes) and run the following command in shell:

```
chmod a+x lts-1.0.0-Linux-x86_64.sh;
lts-1.0.0-Linux-x86_64.sh -b -p user_specified_installation_path;
```

	* Note: `user_specified_installation_path` is the path where you install the software

2. Test if installation is correct:

```	
user_specified_installation_path/bin/lts-analysis -v
```

	* Note: if correctly installed, the version message will be seen,in this case, `v1.0.0`


##	2. Usage and examples

#### Usage

The following command is used to compare two microbial communities (infileA and infileB) and get the community structure variations.

```
user_specified_installation_path/bin/lts-analysis -a infileA -b infileB -o user_specified_output_path;
```

	* `infileA` is your input file, which describes the composition of your first microbial community. An example was shown in the [example](https://github.com/HuLong-BI/LTS-analysis/tree/master/examples) folder. This file should be strictly formatted as required: 
		* two columns with "Species" and "Reads" as names, seperated by tab.
		* the "Species" column should be character strings recording microbes' names; No dupilicates was allowed. 
		* the "Reads" column should be non-zero integers. 

	* `infileB` is your input file, which describes the composition of your second microbial community, which is treated as background. An example was shown in the [example](https://github.com/HuLong-BI/LTS-analysis/tree/master/examples) folder. This file should be formatted as `infileA`;

	* `user_specified_output_path` is a folder that will be created (if the user didn't create it already) to save your output file `infileA__infileB.spes`. The output file recorded community structure variation results of comparing `infileA` to `infileB`.


#### An example:

Assuming we are at your working directory and we want to compare two microbial communities (i.e.,`infileA.txt` and `infileB.txt`), and store their community structure variation results (i.e., `infileA__infileB.spes`) to the subfolder of `outdir`, the commandline would be:
```
user_specified_installation_path/bin/lts-analysis -a ./infileA.txt -b ./infileB.txt -o ./outdir/;
```

Example input and output files could be obtained from the [examples] (https://github.com/HuLong-BI/LTS-analysis/tree/master/examples) folder.


## 3. Contact
==========

Long Hu <hulongptp@gmail.com>
