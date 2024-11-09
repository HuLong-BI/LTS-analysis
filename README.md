# KIISS algorithm

## 0. About KIISS algorithm

Metagenomic sequencing provides a hypothesis-free profile of biodiversity but is hindered by the kitome—background nucleic acids that obscure the true signal. Accurate interpretation of the data hinges on efficient decontamination, which has to harness a stable, kitome-intrinsic characteristic that is invariant to sample input variations, to ensure robust noise reduction. We discovered that the pairwise ratios of contaminants are stable despite variations in input, in contrast, the individual abundance of contaminant microbes is susceptible to input fluctuations. Based on this, we developed the KIISS algorithm (Kitome Isolation via Intra-sample Similar Subgroups). The KIISS algorithm not only prevents overtreatment by eliminating false positives but also detects overlooked true signals, as demonstrated by its ability to accurately differentiate between common contaminants and actual pathogens in blood and CSF specimens and to identify low-abundance impurity from the supposed-to-be-pure sample. In conclusion, by eliminating kitome, KIISS enhances the fidelity of hypothesis-free metagenomic data and enables straightforward data interpretation.

## 1. Installation

####	System requirements

1. 64-bit computer
2. 1 GB disk space or higher
3. 16 GB Mem or higher
4. Linux (CentOS Linux release 7.4 or higher)

####	Installing

1. Download the codes from [releases](https://github.com/HuLong-BI/LTS-analysis/releases/tag/InstallationFilev1.0.0) and run the following command in shell:

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

The following command is used to compare the test sample to the negative control (infileA and infileB) and get truth signal.

```
user_specified_installation_path/bin/lts-analysis -a infileA -b infileB -o user_specified_output_path;
```

>`infileA` is your input file, which describes the microbial composition of your test sample. An example was shown in the [example](https://github.com/HuLong-BI/LTS-analysis/tree/master/examples) folder. This file should be strictly formatted as required: 
> 1. two columns with "Species" and "Reads" as names, seperated by tab.
> 2. the "Species" column should be character strings recording microbes' names; No dupilicates was allowed. 
> 3. the "Reads" column should be non-zero integers. 

>`infileB` is your input file, which describes the microbial composition of your negative control. An example was shown in the [example](https://github.com/HuLong-BI/LTS-analysis/tree/master/examples) folder. This file should be formatted as `infileA`;

>`user_specified_output_path` is a folder that will be created (if the user didn't create it already) to save your output file `infileA__infileB.spes`. The output file recorded the genuine truth of comparing `infileA` to `infileB`.


#### An example:

Assuming we are at your working directory and we want to compare the test sample to the negative control (i.e.,`infileA.txt` and `infileB.txt`), and to store the genuine truth of the test sample (i.e., `infileA__infileB.spes`) to the subfolder of `outdir`, the command line would be:
```
user_specified_installation_path/bin/lts-analysis -a ./infileA.txt -b ./infileB.txt -o ./outdir/;
```

Example input and output files could be obtained from the [examples](https://github.com/HuLong-BI/LTS-analysis/tree/master/examples) folder.


## 3. Contact
==========

Long Hu <hulongptp@gmail.com>
