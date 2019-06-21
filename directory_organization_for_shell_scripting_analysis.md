# Introduction to structured directory organization for analysis in Bash

This write up is based on computational knowledge passed down by [Konrad](https://github.com/konrad)  
A scientic paper to support this methods can be found [here](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1000424)

## Objective of scripting

The first rule of everything; "always start with why"
There are two main objectives we try to achieve
- Reproducibility
	- Other people can easily use your pipeline or reproduce your work
- Smooth later retrieval
	- Very important for your mental state [pun intended] but you will always revisit code and as such it's easier to understand what you did and if you need to modify stuffs

# Directory Structure

The directory structure should look like this: 
 
```
DateMainProjectWasInitiated-DescriptiveNameofMainProject
├── analyses
│   ├── DateAnalysisWasInitiated-TitleofAnalysis
│   │   ├── bin
│   │   ├── data
│   │   ├── run.sh
│   │   └── docs
├── data
├── bin
└── README.md
```

A bash script that can be used to generate such a directory structure is provided [here](https://github.com/konrad/project_generator) by [Konrad](https://github.com/konrad) 

# Directory structure explained

A typical example will look like this:  

```
2019-08-12-Coxiella_burnetii_species_comparison
├── analyses
│   ├── 2019-08-14-SNP_calling
│   │   ├── bin
│   │   ├── data
│   │   ├── run.sh
│   │   └── docs
│   ├── 2019-08-16-IS1111_blast
│   │   ├── input
│   │   ├── output
│   │   ├── run.sh
│   │   └── docs
├── data
├── bin
└── README.md
```
- The main directory contain 3 subdirectories (analyses, bin, data) and a README.md file (A description of the project)
- The analyses directory usually contains all the subdirectories for different analyses
- Each subdirectory under analyses should have 1 compulsory element (run.sh) the remaining directories could be flexible
- The run.sh is the central element in every analysis. Essentially it's the blue print for what was done and how it was donea detailed description will be provided shortly
