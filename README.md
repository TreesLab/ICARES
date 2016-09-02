## ICARES
###### Version: 0.6.1
##### The Identification of the Cis-Acting RNA Editing Sites.

### 1. Requirement
- Operating system: Linux or Mac 
- [Python 2.7.x](https://www.python.org/downloads/)

    To know your Python version, please open the terminal and type "python2 -V".

- Linux commands: cat, awk, mkdir, echo, grep, sed, cut, sort, uniq, and for loop.


### 2. Usage
```
Usage:
    ./ICARES.sh [SAMPLE_LIST] [GENE_REGION] [MEF_FILE] [WORK_SPACE] 
```

#### 2.1. Preparation
There are three files need to be prepared before running ICARES.
##### Sample list
The first file is the list of the "10-column" pileup files generated by [Samtools](http://www.htslib.org/) on all samples.
```
/path/to/sample_A.pileup
/path/to/sample_B.pileup
/path/to/sample_C.pileup
...
```

##### Genic region
The second file is the information of genic regions, and the format is as the following:
```
1   10007376    10007694    +   ENSG00000202415
1   100111499   100160097   +   ENSG00000099260
1   100163798   100164734   +   ENSG00000223656
1   100174259   100232187   -   ENSG00000156869
1   100250296   100250441   -   ENSG00000201491
...
```
You may download the data from [ENSEMBL Biomart](http://www.ensembl.org/index.html).

##### Mapping error set
The mapping error sets can be downloaded from our FTP site: ftp://treeslab1.genomics.sinica.edu.tw/ICARES/MEF/

#### 2.2. Quick Start
If the three files described above have been prepared (eg. "sample.list", "human\_ensembl\_75.genic\_region", and "hsa.MEF"),
then we may run ICARES with the following command:

```bash
> ./ICARES.sh sample.list human_ensembl_75.genic_region hsa.MEF Output
```

### 3. Output
For the result, please check these two files "all\_MEFok.sort.all.clustering.re\_clustering.nmm" and "nmm.log".
The former records the final candidates of editing sites, and the latter is the log file with numbers of candidates for each type.




