# Hands-on Manual Genome Curation Physalia course - Day 3

**Session 3.2: Dual Curation and curated fasta file generation**

Please find slides for Manual Genome Curation overview and Asssembly Metrics at [Session_3.2_Generating_curated_fasta.pdf](Session_3.2_Generating_curated_fasta.pdf).


Please download the data we are going to use in this session, as follows:


```
wget https://asg_hubs.cog.sanger.ac.uk/physalia_workshop/Day_3.tar.xz
```

Then:

```
tar xvfJ Day_3.tar.xz
```



## Now we have 3 dual haplotype curation maps for curation:

Choose one of the following to work on:

- ilPhyMess1 (lepidoptera): Does this sample come from the homo or heterogametic sex? Which would the sex chromosomes be?
- ilProSehe1 (lepidoptera): Does this sample come from the homo or heterogametic sex? Check for Nucmer alignment for sex chromosome identification.
- laPotLuce1 (monocot): what do you the faded paralell lines among some of the chromosomes would be?


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

```
-o: output file name (it must end in '.fa') 
```

Let's assume you chose to name your output file as 'curated'. Then, the main output files will be:

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




