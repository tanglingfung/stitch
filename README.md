
# Stitch

Austin Glenn Davis-Richardson
<harekrishna@gmail.com>

An experiment:

Illumina sequencing has the ability to generate paired-end reads.  If the sum of the DNA fragments is roughly less than that of 2x an illumina read (~100bp),  they can be said to "overlap."  This script also preserves the quality scores (the 5'-most overrides the 3'-most)

This script uses BLAST to find how a set of paired end reads overlaps, and then writes out a contig based on the best BLAST hit.

This script is extremely slow.  Probably because it has to write files for each paired-end read, causing a lot of lag.

I eventually gave up as I found an assembly program that supports overlapping paired end reads.

Perhaps this work will be useful to someone else in the future.  Some portions of the script can be used for other general bioinformatics tasks such as dnaobj.py but I'm sure you'll just want to use BioPython anyway.

I've since stopped working on this.  If you want me to start again, ask nicely.

## Usage

python test.py fastqfile1 fastqfile2 contigfile contig_failed_file

Where fastqfile1 is the 5' most and fastqfile2 is the 3' most

## Files

 - dnaobj.py - object representing a FASTA or FASTQ record
 - doubleblast.py - Uses NCBI+ bl2seq to perform a blast between two sequences.
 - fastitr.py - Iterates through a FASTA/Q file, generating dnaobj objects
 - gcblast.py - This was to be the main script
 - test.py - This IS the main script right now.

## Pre-reqs

Uses blast+ 2.2.23 from NCBI

## Know your rights

Stitch is free and open-source.
See LICENSE file (GNU GPL v3)