# Hands-on Manual Genome Curation Physalia course - Day 2

**Session 3: Beginning manual curation (Single haplotype curation)**

Please find today's slides at docs/Session_3_Beginning Manual Curation.pdf.

Now you need to download the data we are going to use in this session. You can download it to GitPod or locally to your laptop, as follows:
```
wget https://asg_hubs.cog.sanger.ac.uk/physalia_workshop/Day_2.tar.xz
tar xvfJ Day_2.tar.xz
```

**Start practicing manual curation on 3 insect genomes. These will be all single haplotype maps.**

Choose one of the following to start:

- icSchPect1 (coleoptera)
- icPolPter2 (coleoptera)
- ieProBifi1 (ephemeroptera): can you spot something unexpected on the HiC map, maybe something that you try to fix, but it never looks right?

Check if these genomes belong to homogametic or heterogametic samples and try to identify and assign sex chromosomes. You may use Nucmer output files or PacBio reads coverage.

> [!IMPORTANT]
> At the end of the curation process, check if you:
> 1. Made all the necessary rearrangements in the map
> 2. Added metadata
> 3. Painted chromosomes
> 4. Generated AGP file
