---
title:  "Informatics Challenge! 2023"
date: "`r format(Sys.time(), '%m/%d/%Y')`"
output:
    html_document:
        toc: true
        toc_float: true
        toc_depth: 3
        number_sections: true
        code_folding: hide
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

# How the informatics challenge will work

Welcome to the 2023 annual informatics challenge!

The purpose of this is to have some fun trying out things that you might not
have previously tried, and to learn something new. It's also a contest, so you
will have the chance to win fabulous* prizes**!

Below are a series of questions of varying difficulty. Each question will be
worth varying points. Some of these questions are language specific, while
others can be completed however you'd like. Either way,

**please show your work/code**.

I'm writing the questions to be either a task or specific question, such that
it is unambiguous if the answer is right. If you do the task or answer the
question correctly you get full points. No partial credit.

I am asking participants to specify their experience level to split folks
into two categories. I'll be awarding two trophies, one for each category.

-  Beginners are those that are just getting started and have been doing
informatics regularly for a year or less.
-  You should likely submit as Advanced if you have been doing this for a while
and if all the beginner questions seem really easy and the harder questions
don't seem too bad.

I'm giving two weeks to complete everything. You don't have to complete all the
questions, I'll be defining winners of the two categories based on the highest
total points. If you're the only one who enters, you can win by answering just
one question! Last year there was only one person in the beginner category, so
they won by default!

Feel free to do internet searches to figure things out, though I'm asking that
you **don't use chat-GPT or any AI methods** to generate your answers as you
won't learn anything from that (and that's half the point of all this).

You can put your answers in-line in the Rmd file or you can provide your answers
another way if you prefer.

**The due date will be April 18th at 11:59 PM**

Feel free to ask for clarification on anything!

------------------------------------------------------------------------

## Are you submitting in the beginner or advanced category?

------------------------------------------------------------------------

# Git and GitHub - 5 points per question
1.  For your submission, fork my repository (https://urldefense.com/v3/__https://github.com/MVesuviusC/2023_informatics_challenge__;!!AU3bcTlGKuA!FyV8Z0KoKPYYzewFPMBjR0MrfJhaw43GsI99WxAS0OAM6BBufwVj9vBavnoaBxwEe9hP9b7YGt2BhjIGYMYSI72_JIZ6Iz0RAjLxH4EVq0M$ ) and send me a link to your fork with your results in a public GitHub repository

2.  Make sure your repo includes at least two branches and two commits, with one of your new branches merged back into your main branch

# Beginner questions - 1 point per question

## Basic R data and variable types
3.  Make a variable containing a vector of five names
```{r}
names = c("Alex", "Peter", "Maria", "James", "John")
names
```
4.  Make a variable containing a boolean vector where two elements are true and three are false
```{r}
bool = c(TRUE, FALSE, FALSE, TRUE, FALSE)
bool
```

5.  Use the varible with the boolean values to subset the names variable down to two names inside a new variable
```{r}
subset = names[bool]
subset
```

6.  Create a varible containing a numeric matrix (10 rows and 10 columns) of random numbers

```{r}
matrix = matrix(rnorm(100) , nrow = 10)
matrix
```
7.  Add 1 to every element in your numeric matrix in a single line of code
```{r}
matrix + 1
```

## Sequencing basics

8.  When doing Illumina sequencing, what is the purpose of the "index" read?

Indexing Illumina libraries allows for multiple libraries to be pooled and sequenced simultaneously on the same flow cell, as each index serves as a unique identifier for each library. 


9.  What is the difference between single-ended and paired-ended sequencing?

Single-ended sequencing produces a sequence from one end of the molecule, whereas paired-end sequencing produces 2 sequences from both ends of the fragment. Paired-end sequencing is better suited for mapping repetitive regions. 


## Make basic plots
You can access a dataset in R using the following code (you'll need the dplyr or tidyverse package installed):

```{r}
storms <- dplyr::storms
```

10.  Using the storms data, make a scatterplot of wind vs pressure

```{r}
plot(storms$wind, storms$pressure)
```

11.  Using the storms data again, make a histogram of pressure

```{r}
hist(storms$pressure)
```

## Statistics
12.  Using the storms data, perform a linear regression on the pressure to determine if wind speed is correlated with pressure

```{r}
result = lm(storms$wind ~ storms$pressure)

summary(result)
```

13.  When performing PCA, how do you know how many principal components to use for further analysis?

You can make a scree plot and figure out at which number of principal components there is an inflection in the plot, and that's #the number of principal components to be used for further analysis.

14.  What is the purpose of performing a variance stabilization transformation of gene expression values in RNAseq?

To check for outliers in the data

15.  In statistical terms, what is alpha-level ($\alpha$)?

Alpha-level is the level of significance, or the probability of rejecting a null hypothesis when it's indeed true. 

16.  If a given event has a probability of success of 0.1, what is the probability of at least one success given three attempts, assuming that each trial is independant?

0.1 * 1 * 1 = 0.1 probability

## Basic unix commands

17.  Which single command would you use to change directories from `~/` to `~/data/expt1/pcrs/`?

cd data/expt1/pcrs/

18.  How do you change permissions on a file to disallow all other users from reading it?

chmod 733

19.  How do you rename a file?

mv old_filename new_filename

20.  What command creates a new empty file?

touch

21.  How do you make a varible in bash?

Use "=", the assignment operator. E.g. my_var = 1. 

## Basic file/data formats

22.  What file/data format is this?

VCF 

```{verbatim, max.height='100px'}
chr10   18595   .       A       .       285     PASS    DP=48;MQSB=1;MQ0F=0;AN=2;DP4=24,24,0,0;MQ=60    GT:DP   0/0:48
chr10   18596   .       C       .       285     PASS    DP=48;MQSB=1;MQ0F=0;AN=2;DP4=23,24,0,0;MQ=60    GT:DP   0/0:47
chr10   18597   .       C       .       285     PASS    DP=49;MQSB=1;MQ0F=0;AN=2;DP4=25,24,0,0;MQ=60    GT:DP   0/0:49
chr10   18598   .       T       .       285     PASS    DP=49;MQSB=1;MQ0F=0;AN=2;DP4=25,24,0,0;MQ=60    GT:DP   0/0:49
chr10   18599   .       G       .       285     PASS    DP=53;MQSB=1;MQ0F=0;AN=2;DP4=25,27,0,0;MQ=60    GT:DP   0/0:52
chr10   18600   .       C       .       285     PASS    DP=53;MQSB=1;MQ0F=0;AN=2;DP4=25,27,0,0;MQ=60    GT:DP   0/0:52
chr10   18601   .       A       .       285     PASS    DP=53;MQSB=1;MQ0F=0;AN=2;DP4=25,27,0,0;MQ=60    GT:DP   0/0:52
chr10   18602   .       G       .       285     PASS    DP=53;MQSB=1;MQ0F=0;AN=2;DP4=26,27,0,0;MQ=60    GT:DP   0/0:53
```

23.  What file/data format is this?

```{verbatim, max.height='100px'}
chr1_KZ114997v1_alt     4592    N       10      AAAAAaAAAA      II1HIIHIDB
chr1_KZ114997v1_alt     4593    N       10      GGGGGgGGGG      IICFIIIIDD
chr1_KZ114997v1_alt     4594    N       10      CCCCCcCCCC      IIHHIIIIII
chr1_KZ114997v1_alt     4595    N       10      TTTTTtTTTT      IIHIIGII@I
chr1_KZ114997v1_alt     4596    N       11      GGGGGgGGGG^]G   IIHHIIIICID
chr1_KZ114997v1_alt     4597    N       11      CCCCCcCCCCC     IIEGIIII@IA
chr1_KZ114997v1_alt     4598    N       11      AAAAAaAAAAA     II@HIIIICHB
chr1_KZ114997v1_alt     4599    N       11      GGGGGgGGGGG     IIGHIHIIDI@
chr1_KZ114997v1_alt     4600    N       11      GGGGGgGGGGG     IIEHIHIIHHD
chr1_KZ114997v1_alt     4601    N       11      AAAAAaAAAAA     II=HIHIIHI=
chr1_KZ114997v1_alt     4602    N       11      T$TTTTtTTTTT    IIGEIHIIHIH
```

24.  What file/data format is this?

FASTQ

```{verbatim, max.height='100px'}
@A00498:356:H53CMDRXY:1:2101:1859:1016 1:N:0:CTGACGCG
CTGACGCG
+
FFFFFFFF
@A00498:356:H53CMDRXY:1:2101:2184:1016 1:N:0:CTGACGCG
CTGACGCG
+
FFF:FFFF
@A00498:356:H53CMDRXY:1:2101:2220:1016 1:N:0:CTGACGCG
CTGACGCG
+
FFFFFFFF
@A00498:356:H53CMDRXY:1:2101:2745:1016 1:N:0:CTGACGCG
CTGACGCG
+
FFFFFFFF
```

25.  These sequences are all from the same file. What is a possible reason that these sequences are not all the same length?

Sequences from two organisms were sequenced simultaneously, i.e. like a spike in control. 

```{verbatim, max.height='100px'}
@A00498:586:HWWJ3DRX2:1:2101:7238:1063 1:N:0:ATTACTCG+AGGCTATA
TNTGGCTACACTCCAGATCGCAATATTTGTTTTCATGATGATCTGGGTACTGCCAGCAAGGCTCAGTAGAGTAAATGGTATCAAAAGCAGGATCCTCCAGTTACTTTTCCCGATCTCCATCCAAATATTTTCAGGGGTCAACCTGTACTTC
+
F#F:FF,F:FFFF::FFFFFF:FFFF,FF:FFFFF:,FFFFFFFF:FFF:F,F:FFFF:F,F,FFF,FFF,:FF,,F,FF:FFFFF,FF::F,:FFFFF:,F,FF,FF:,FF,FFF:,FFFF,FFFFFFF,F:,F,FF:FF,F:FFF:FF:
@A00498:586:HWWJ3DRX2:1:2101:7274:1063 1:N:0:ATTACTCG+AGGCTATA
CNGTCTTTCTGAGAAAGCAGCTGCAGCCTCCGTAAGGACAGAGGTCAGGCCTGATGCATCCTAGAATCTTC
+
F#F:FFFFFFFFFFFFFFFFFFFFF,F,FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF
@A00498:586:HWWJ3DRX2:1:2101:7419:1063 1:N:0:ATTACTCG+CGGCTATA
TNTTTTTTGAGACGGAGTTTCGCTCTTATTGCCCAGGCTGGAGTGCCATGGCGTGATCTCGGCTCACCACAACCTCCGCCTCCCAGGTTCAAGTGATTCTCCTGCCTCAGCCTCCCGAGTAGCTGGGATTACAGGCATTCACCACCATGCC
+
F#FFFFFFFFFFFFFFFF:FFFFFF:F,FFFFFFF:F,FFFFFFF:FFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFF:FFFFFFFFFFFFFFF:FFF:F,FFFFFFFFFFFFFF:FFFFFF:F:FFFFFFF,FFFF:FFFF
@A00498:586:HWWJ3DRX2:1:2101:7618:1063 1:N:0:ATTACTCG+CGGCTATA
TNAAAGAACGCATTTGCACAGCATTACAGATCGCAGGCGGTAGCATGACTTAT
+
F#FFFFFFFFFFFFFFFFFFFFFFF:F,FFFFFFFFFFFFFFFFFFFFFFFFF
```

26.  In the previous question, what information does "1:N:0:ATTACTCG+AGGCTATA" represent in the header line?

1 means it's read 1 from a pair, N means the read passed the filtering criteria, 0 is a control number, sequences are indices


## Basic troubleshooting
27.  I started a new R session and ran the following code and got the following error:
Fix my mistake and explain what I did wrong.
```{r}
install.packages(ggplot2)
library(ggplot2)

ggplot(mtcars, aes(x = cyl, y = mpg)) +
    geom_point()

Error in ggplot(mtcars, aes(x = cyl, y = mpg)) : 
  could not find function "ggplot"
```

Forgot to install and/or load the ggplot2 package

28.  I started a new R session and ran the following code:
```{r}
summary(mtcars$cy1)
```

I didn't get an error, but this output doesn't look right. What is wrong with the code and how can I fix it?
```{verbatim, max.height='100px'}
Length  Class   Mode 
     0   NULL   NULL
```

Mispelling -- wrote cy1 instead of cyl

Instead:

```{r}
summary(mtcars$cyl)
```

29.  I ran the following code and got this error:
Fix my mistake and explain what I did wrong.
```{r}
cutoff_val <- 0.05
pval <- 0.0001

if (pval < cutoff_val & pval >= 0.001) {
    print("Significant")
# the variable to compare is missing, i.e. pval  
} else if (pval < 0.001) {
    print("Very significant")
} else {
    print("Not significant")
}
#Error: unexpected '<' in:
#"    print("Significant")
#} else if (<"
#>     print("Very significant")
#[1] "Very significant"
#> } else {
#Error: unexpected '}' in "}"
#>     print("Not significant")
#[1] "Not significant"
#> }
#Error: unexpected '}' in "}"
```

Forgot to include pval (variable) for evaluation

------------------------------------------------------------------------

# Intermediate - 2 points per question

## Sequences
30.  TRUE or FALSE. When aligning fastq files to a reference, each pair of R1 and R2 reads (reads that have the same header) must be the same sequence length.

TRUE

## Make fancy plots
31.  Using the storms data, make a jitter plot where x is a categorical variable of the wind speed (in bins of 10 knots per bin) and y is pressure. Be sure the colors used are color-blind friendly.

```{r}
min(storms$wind)

max(storms$wind)

storms = storms%>%
  mutate(wind_binned = ifelse(wind <= 10, "0-10", ifelse(wind <= 20, "11-20", ifelse(wind <= 30, "21-30", ifelse(wind <= 40, "31-40", ifelse(wind <= 50, "41-50", ifelse(wind <= 60, "51-60", ifelse(wind <= 70, "61-70", ifelse(wind <= 80, "71-80", ifelse(wind <= 90, "81-90", ifelse(wind <= 100, "91-100", ifelse(wind <= 110, "101-110", ifelse(wind <= 120, "111-120", ifelse(wind <= 130, "121-130", ifelse(wind <= 140, "131-140", ifelse(wind <= 150, "141-150", "151-160"))))))))))))))))

storms$wind_binned = factor(storms$wind_binned, levels = c("0-10", "11-20", "21-30", "31-40", "41-50", "51-60", "61-70", "71-80", "81-90", "91-100", "101-110", "111-120", "121-130", "131-140", "141-150", "151-160"))

plot = ggplot(storms, aes(x = wind_binned, y = pressure, color = wind_binned))+
  geom_jitter()+
  xlab(label = "Wind in Knots")+
  scale_color_manual(values = c("black", "#E69F00", "#56B4E9", "#009E73", "#F0E442", "#0072B2", "#D55E00", "#CC79A7", "black", "#E69F00", "#56B4E9", "#009E73", "#F0E442", "#0072B2", "#D55E00", "#CC79A7"))
plot
```
32.  Use plotly to create an interactive plot of the dplyr::starwars data where x is homeworld and y = height. On mouseover, name, height and mass should be displayed. Save the plot as an html file.


33.  Make a panel of four plots in a single png file where the plots use geom_point(), geom_histogram(), geom_density(), and geom_boxplot() using the storms dataset. The plots should be arranged in a 2x2 grid.

```{r}
library(cowplot)

pl1 = ggplot(storms, aes(x = wind, y = pressure))+
  geom_point()
pl1 

pl2 = ggplot(storms, aes(x = year))+
  geom_histogram(binwidth = 2)
pl2

pl3 = ggplot(storms, aes(x = year))+
  geom_density()
pl3  

pl4 = ggplot(storms, aes(x = status, y = wind))+
  geom_boxplot()
pl4

png("plots_combined.png")

plot_grid(pl1, pl2, pl3, pl4, align = "hv", axis = "tbrl", ncol = 2)

dev.off()

```

## Alignment
34.  When aligning reads using HiSat2, when would you use the --phred64 option?

This option is needed when the inputs are ASCII characters which are equal to the Phred quality plus 64.

35.  What does this CIGAR string from a bam file tell you about the alignment?
124M2D25M1S

There are 124 exact matches from the query sequence to the reference sequence followed by a deletion of 2 nucleotides and an eact match of 25 nucleotides with soft clipping present

36.  What does the bitwise flag 163 found in a bam file mean?

## Bash
37.  If you had 1,337 files in a directory and you wanted to change the name of each of them to remove "file_" from their file names, how would you do it in a single line of code (using no semicolons)?


## Intermediate troubleshooting
38.  I ran the following code and got the following error:
Fix my mistake and explain what I did wrong.
```{r}
summary(paste(mtcars$mpg, mtcars$disp "mpg vs disp"))
Error: unexpected string constant in "summary(paste(mtcars$mpg, mtcars$disp "mpg vs disp""
```

Forgot to put comma, should be instead:

```{r}
summary(paste(mtcars$mpg, mtcars$disp, "mpg vs disp"))
```


39.  I ran the following code and got the following warning:
Should I be concerned about this warning?
If so, fix my mistake and explain what I did wrong.
```{r}
col_names <- colnames(mtcars)

for (i in 1:12) {
    print(max(mtcars[[col_names[i]]]))
}
[1] 33.9
[1] 8
[1] 472
[1] 335
[1] 4.93
[1] 5.424
[1] 22.9
[1] 1
[1] 1
[1] 5
[1] 8
[1] -Inf
Warning message:
In max(mtcars[[col_names[i]]]) :
  no non-missing arguments to max; returning -Inf
```
This warning is not too big of a deal, there is no error per se, the code loops through columns 1 through 12, however, there are only 11 columns, so it's calculating a maximum of a column that doesn't exist. 

Instead:

```{r}
col_names <- colnames(mtcars)

for (i in 1:11) {
    print(max(mtcars[[col_names[i]]]))
}
```

40.  I wrote a loop to make a bunch of plots, but when I run it, nothing is plotted.
Fix my code and explain what I did wrong.
```{r}
for (col_name in c("mpg", "disp", "hp")) {
    ggplot(mtcars, aes(x = col_name, y = wt)) +
        geom_point()
}
```
Print statement is needed for the plots to be displayed. 

Instead:

```{r}
for (col_name in c("mpg", "disp", "hp")) {
    plot = ggplot(mtcars, aes(x = col_name, y = wt)) +
        geom_point()
    print(plot)
}
```


# Hard - 3 points per question

## R stats
41.  When doing a statistical test in R, if you see a p-value of 2.2e-16, what is the special importance of this value compared to any other p-value you might see?

That while this value may be printed, the actual p value might be diffrerent (and may be able to be retrieved with test$pvalue or something similar), it happens due to a default setting in R that sets any number smaller than the .Machine$double.eps to 2.2e-16.

42.  TRUE or FALSE. When doing a statistical test in R, if you see a p-value of 0.05, this means that there is a 5% chance that the null hypothesis is true

FALSE

## 10x single-cell sequencing
43.  When sequencing a library created using the 3' 10X kit, what are the recommended sequence lengths for R1, R2, I1 and I2?

## R objects
44.  Create a S4 R object to hold the data contained in a single sequence in fastq format

45.  Create a method for your S4 object to trim the fastq sequence and quality fields to a length provided as an argument

46.  Create another class that has a slot to contain a list of your S4 fastq objects, and has a method to read in a fastq file provided as an argument. Create other slots in the object to: 1) contain the number of fastq sequences in the object and 2) store the min/max sequence length found across all fastq sequences (single min/max across the whole dataset, not min/max per sequence).

## Harder plotting
47.  Use the storms data to make a plot with a single line for each named storm, where x is the latitude and y is the longitude. The line should trace the storm's path across time. Color the path by the pressure.


## Get data from NCBI
48.  Get the data from SRA #SRR23690179, align to the mouse genome and call SNPs.

49.  Get the data from GEO #GSE200744, do PCA on the normalized data and make a single plot showing the first ten principle components, but don't make the traditional PC1 vs PC2 scatterplots. Color each point by normal, met or premet status.

## R loops
50.  I have a table of information saved in a variable called `ref_info` (below). Loop over each row of this table and make plots using the storms dataset with the relevant parameters. For instance the code first plot should be something like this:

```{r}
ggplot(storms,
       aes(x = year, y = pressure)) +
  geom_point() +
  scale_y_log10() +
  labs(title = "Pressure for Hurricane Irma",
       y = "Pressure (log10)",
       x = "Year")
```

```{r}
ref_info <-
    tribble(~ y_column_name,
            ~ x_column_name,
            ~ y_data_transform,
            ~ plot_title,
            ~ y_axis_label,
            ~ x_axis_label,

            "pressure",
            "year",
            "log10",
            "Pressure by Year",
            "Pressure (log10)",
            "Year",

            "pressure",
            "month",
            "log10",
            "Pressure by Month",
            "Pressure (log10)",
            "Year",

            "wind",
            "pressure",
            "none",
            "Wind speed vs Pressure",
            "Wind speed (knots)",
            "Pressure",

            "wind",
            "status",
            "Multiply by 1.15078",
            "Wind Speed by Storm Type",
            "Wind Speed (mph)",
            "Storm Type")
```


## Harder troubleshooting
51.  I ran the following code and got the following error:
Fix my mistake so that the plot is generated and explain what I did wrong.
```{r}
library(tidyverse)
library(GenomicFeatures)
library(EnsDb.Hsapiens.v86)

transcript_data <-
    transcripts(EnsDb.Hsapiens.v86) %>%
    as.data.frame()

mutate(transcript_data,
       seqnames = droplevels(seqnames)) %>%
    mutate(chrom = paste0("chr_", seqnames)) %>%
    rename(Chromosome = chrom) %>%
    filter(grepl("^[0-9XYM]", test$seqname, perl = TRUE)) %>%
    ggplot(aes(y = Chromosome,
               x = start,
               color = log10(width))) +
    geom_point() +
    theme_bw()
Error in rename(., Chromosome = chrom) : object 'chrom' not found
```

## Bash variable expansion
52.  Create a bash array with made up file names, then loop over the array and print out both the file name and the file name without the extension (.txt, .gz, etc.) for each.

```{verbatim}
file_array=("file1.csv" "file2.txt" "file3.csv" "file4.txt")

for file in ${file_array[@]}; do
  echo $file
  echo ${file%.*}
done
```

53.  Provide code to locate all uncompressed ".txt", ".sam", ".tsv" and ".csv" files in your home directory (and all downstream subdirectories) and compress them. Do this only for files larger than 5 MB.

------------------------------------------------------------------------

# Too hard - 4 points per question

## PCA interpretation
54.  I've attached an image of a PCA plot that I made (odd_pca.png). How would you interpret the shape of the distribution of points in this plot? What does it tell you about the data?


I think this PCA originates from data that represents temporal transition from one state to another. I would interpret this plot as having variance that gradually changes from one cell state to another cell state. 

## Super fancy plot
55. Remake your plot of storm paths above, but put a map of the world in the background, with accurate lat/long locations

## Very hard troubleshooting
56.  I wrote a loop to make plots, but got this error:
```{r}
[1] "1978 wind range: 10 160"
[1] "1978 pressure range: 882 1022"
Error in 2023 - year : non-numeric argument to binary operator
```
Once you fix that error, your plots will all come out the same, even though they shouldn't.

What is wrong with my code? Explain and fix it so the four plots show the proper distributions, while still using the loops to create the plots.

Note:
    - For each year, the two histograms should look different
    - The distribution in all four histograms should be different
    - Pay attention to the ranges printed out inside the loop compared to your plots
```{r}
#1). Years were specified as factors, and not as numeric variables 
library(dplyr)
library(patchwork)
years <- c(1978, 2020)
plot_list <- list()

for (year in years) {
    print(paste(year,
                "wind range:",
                min(storms[which(storms$year == year), ]$wind),
                max(storms[which(storms$year == year), ]$wind)))
    print(paste(year,
                "pressure range:",
                min(storms[which(storms$year == year), ]$pressure),
                max(storms[which(storms$year == year), ]$pressure)))
    print(2023 - year)

    for (limit in c("pressure", "wind")) {
        title_text <- paste("Pressure from Storms in ", year)
        print(limit)
        print(year)
        print(class(year))
        plot_list[[paste(year, limit)]] <-
            storms %>%
            filter(!!year == year) %>%
            ggplot(aes(x = get(limit))) 
        
            storms_upd = storms%>%
              filter(!!year == year)
            print(storms_upd)
            geom_histogram(bins = 100) +
            labs(title = title_text,
                y = "Count",
                x = str_to_title(limit))
    }
}

(plot_list[[1]] + plot_list[[2]]) / (plot_list[[3]] + plot_list[[4]])
# Why are they all the same!?!?!?!?
message("You hear maniacal laughter in the distance...")
```


------------------------------------------------------------------------

# I hate myself - 10 point per question

## Animate a plot
57. Remake your plot of the storm paths, with the map of the world in the background, but animate it so that each frame of the animation is a day of the year starting at Jan 1st and going through the full year. All years should be plotted simultaneously. Save your results as a gif.

## Identify the mystery data type
58.  On the Franklin cluster is a folder /gpfs0/scratch/mvc002/. Inside this
folder are two files:
  -   mysteryData_R1.bam
  -   mysteryData_R2.bam
  These files are alignments for R1 and R2 from a single dataset. What type of data are these data derived from?

59.  There is another file named mysteryData_otherData.bam in the same folder. What type of data is this file derived from?

## Harder programming
In /gpfs0/scratch/mvc002/ there is a bcf file: 'info_challenge.bcf'. This file has SNP calls for 29 samples. I want to calculate average pairwise distances between all samples, counting the number of differing alleles at each position covered in both samples across the whole genome, then dividing by the number of comparisons for each pair of samples.
For instance:
given the last four columns from a single line in the file:

1/1:189,255,0:168:127   1/0:208,255,0:178:127   0/1:183,255,0:140:127   ./.:186,255,0:105:127

The first sample differs from the second at one allele, from the third at two alleles and the fourth at unknown alleles.
For each position, ignore any comparison where one of the two samples isn't covered ("./.").
Since the data aren't phased, treat 0/1 and 1/0 as identical.
Remember that for each position, we are comparing two alleles, so the number of comparisons will be the number of shared sites (for each pair of samples) times two.

This means the matrix of the distance for this position would be:
0   1   1   NaN
1   0   0   NaN
1   0   0   NaN
NaN NaN NaN NaN

And the number of compared alleles would be:
2   2   2   NaN
2   2   2   NaN
2   2   2   NaN
NaN NaN NaN NaN

Your results should be a 29x29 matrix with the average pairwise distances between all samples across all positions. The correct output from this file is in /gpfs0/scratch/mvc002/info_challenge.distances.txt for reference.

I wrote a script to do this on the provided file and my best time running it on the cluster was just over 2 minutes.

(py3_10) [mvc002@r1pl-hpcf-h03 bioinfoTools]$ time python exec/vcfToMatrix.py --vcf test_sc_data.bcf -p 48

real    2m2.622s
user    89m19.035s
sys     1m10.783s

60.  Write code that does the same thing

61.  Beat my time

62.  AI-generated code is becoming more and more common. It is a very powerful tool, but what is one way that using AI-generated code can be disadvantageous? (This question was written with the assistance of GitHub Copilot.)





























* a plastic
** trophy, though it may be a bit delayed since I'm in the process of fixing my 3D printer. It shouldn't take too long though.
