# Hands-on Manual Genome Curation Physalia course - Day 5

**Session 5: Challenging genomes to curate and strategies to deal with them - Part 2**


Now you need to download the data we are going to use in this session.

```
wget https://asg_hubs.cog.sanger.ac.uk/physalia_workshop/Day_5.tar.xz
```

Then:

```
tar xvfJ Day_5.tar.xz
```



## Today, we are working on dual haplotype maps.

- pySymPilo4: protist with poor HiC and high chromosome number. ``` pySymPilo4_2_normal.pretext ```. Give a try on this puzzle!


**Try your best, saving time at the end to generate the curated fasta file.**


> [!TIP]
> 1. Use the nucmer alignments to assemble the micros (identify the order the scaffolds go to make a full micro)
> 2. Go to tolqc (https://tolqc.cog.sanger.ac.uk) and check the data available for your assembly.

**Which were the main difficulties you found while working on these genomes?**

> [!IMPORTANT]
> At the end of the curation process, check if you:
> 1. Made all the necessary rearrangements in the map
> 2. Added metadata
> 3. Painted chromosomes
> 4. Generated AGP file

## Generating fasta files for single and dual curation maps


Go to the assembly directory.

**Step 1. Run rapid_split on your decontaminated, pre-curation fasta file to create a tpf:**

```

perl /workspace/rapid-curation/rapid_split.pl -fa <your_fasta>.fa

```

Now you have a .tpf file from your original fasta, named original.fa.tpf.


**Step 2. Run pretext-to-tpf (alias ptt):**

To run pretext-to-tpf type the alias ‘ptt’ in the terminal, as the following:

```
ptt -a original.fa.tpf -p <your_species>.agp_1 -o <output_name>.tpf -w -f

```


```
-w: overwrite 
-f: force to run and overwrite
```

Let's assume you chose to name your output file as 'curated'. Then, the output files will be:

**A. Single haplotype:**

```
curated_Haplotigs.tpf
curated_curated.tpf
chrs.csv

```

**Step 3. Run multi_join. This is what generates a new fasta file from the curation manipulations**

**B. Dual curation:**

```
curated_Haplotigs.tpf
curated_HAP1.tpf
curated_HAP2.tpf
chrs_HAP1.csv
chrs_HAP2.csv
curated.log
```


**Output files from dual curation:**

```
<tolid>.hap1.1.all_haplotigs.curated.fa
<tolid>.hap1.1.inter.csv
<tolid>.hap1.1.primary.chromosome.list.csv
<tolid>.hap1.1.primary.curated.fa
<tolid>.hap2.1.all_haplotigs.curated.fa
<tolid>.hap2.1.inter.csv
<tolid>.hap2.1.primary.chromosome.list.csv
<tolid>.hap2.1.primary.curated.fa
```
