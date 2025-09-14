# MapReadCount
Code Summary The following block of code will read in fastq files (able to read in as batch in a folder) and partial left and right adapter sequences or even when no adaptor sequences and extract insert sequence of interest. Extracted sequences are aligned and counted against template sequences provided as a fasta/csv file. Mapping statistic are output in a consolidated csv file.

Used case

Replace FASTQ_FILE with your input file (fastq or fastqz) or point to the folder that contains input files.
Replace TEMPLATE_FILE with your template file (fasta).
Set and adjust parameters before running the code.
Format of input fasta file
>Name_of_template_sequence_1
Template_Sequence_1
...

Functionality

With partial left and right adapter sequences provided, insert sequence of interest is assumed to be immediately adjacent to the adapter sequences.
With no adapter sequences provided, the code will infer the adapter sequences and extract insert sequences.
Extracted sequences will be aligned to the provided template sequences and counted.
The code allows for mismatch thresholds (Hamming / Levenshtein); Deafult Hamming = 2 and LEVENSHTEIN = 3.
Aligned reads are tracked and plotted.
Mapped reads per template: Percent reads that mapped to each template.
adapter matched type: Percent reads that has strict (complete matching), mixed (complete/partial matching) or fuzzy adapters (partial matching).
dist_distributions: Records distances for each alignment method (Hamming or Levenshtein)
Read retention statistics are also output in a csv file.
Other statistics in csv output include:
Total reads, strict, mixed, fuzzy, rc_reads, mapped, unmapped in counts and in percent
