# Hands-on Manual Genome Curation Physalia course - Day 3

**Session 3.2: Dual Curation and curated fasta file generation**

Please find slides for Manual Genome Curation overview and Asssembly Metrics at [Session_3.2_Generating_curated_fasta.pdf](Session_3.2_Generating_curated_fasta.pdf).


Please download the data we are going to use in this session from [here](https://asg_hubs.cog.sanger.ac.uk/physalia_workshop/Day_3.tar.xz). As example like that:


```
wget https://asg_hubs.cog.sanger.ac.uk/physalia_workshop/Day_3.tar.xz
tar xvfJ Day_3.tar.xz
```


## Now we have 3 dual haplotype maps for curation:

Choose one of the following to work on:

- laPotLuce1 (monocot): what do you think the faded paralell lines among some of the chromosomes would be?
- ilPhyMess1 (lepidoptera): Does this sample come from the homo or heterogametic sex? Which would the sex chromosomes be?
- ilProSehe1 (lepidoptera): Does this sample come from the homo or heterogametic sex? Check for Nucmer alignment for sex chromosome identification. For Nucmer, use Dot viewer to visualize the results at: https://dot.sandbox.bio.
The Nucmer results files are here: https://drive.google.com/drive/folders/1pw-bQ5Aj6I-ooll6YHGpOiJjJC552hWW?usp=sharing

> [!TIP]
> 1. The canonical Z should be one of the large scaffolds and in this case, it doesn't show any alignments.
> 2. Even using a species from the same genus as a comparator and Z chromossomes being usually very conserved, there is always the chance of many rearrangements to happen.



> [!TIP]
> Go to tolqc (https://tolqc.cog.sanger.ac.uk) and check data available for your assembly. 
> 1. How much curation effort you expect to be necessary based on heretozygozity? 
> 2. Are PacBio and HiC data from the same sample?


> [!IMPORTANT]
> At the end of the curation process, check if you:
> 1. Made all the necessary rearrangements in the map
> 2. Added metadata
> 3. Painted chromosomes
> 4. Generated AGP file

## Generating fasta files for single and dual curation maps


On your working directory:

**Run pretext-to-asm:**

```
pretext-to-asm -o <fasta>.fa -a <uncurated_fasta>.fa -p <curated_agp_file>.agp_1

```

-o: output file name (it must end in '.fa') 

Then, the main output files will be:

**A. Single haplotype:**

```
<ID>.1.primary.curated.fa
<ID>.1.additional_haplotigs.curated.fa
<ID>.1.primary.chromosome.list.csv

```

**B. Dual curation:**

```
<ID>.hap1.1.primary.curated.fa
<ID>.hap1.1.primary.chromosome.list.csv
<ID>.hap2.1.primary.curated.fa
<ID>.hap2.1.primary.chromosome.list.csv

```




