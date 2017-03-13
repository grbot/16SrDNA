Assessment data info
====================

    ##    Sample Cat Treatment
    ## 1   Cat 2  CI         1
    ## 2   Cat 6  BI         1
    ## 3  Cat 11  CI         2
    ## 4  Cat 15  BI         2
    ## 5  Cat 20  CI         3
    ## 6  Cat 24  BI         3
    ## 7  Cat 29  CI         4
    ## 8  Cat 33  BI         4
    ## 9  Cat 38  CI         5
    ## 10 Cat 42  BI         5
    ## 11 Cat 47  CI         6
    ## 12 Cat 51  BI         6
    ## 13 Cat 56  CI         7
    ## 14 Cat 60  BI         7
    ## 15  Cat 2  CI         1

Two cat samples and each sample went under seven treatments. Based on
the info we got from the training data we can assume *There are seven
cats which are treated with increased percentage of a compound in their
diet. 7 different treatments (1-7, representing an increased percentage
of a compound in their diet)*

Investigating raw read counts
=============================

    ##    Samples_ID Fwd_read_count Rev_read_count Total_count
    ## 1       Cat11         135705         135705      271410
    ## 2       Cat15         121938         121938      243876
    ## 3       Cat20         138085         138085      276170
    ## 4       Cat24         146494         146494      292988
    ## 5       Cat29         138384         138384      276768
    ## 6        Cat2         103819         103819      207638
    ## 7       Cat33         133808         133808      267616
    ## 8       Cat38         131974         131974      263948
    ## 9       Cat42         141054         141054      282108
    ## 10      Cat47         110455         110455      220910
    ## 11      Cat51         132224         132224      264448
    ## 12      Cat56         104119         104119      208238
    ## 13      Cat60          90326          90326      180652
    ## 14       Cat6         120924         120924      241848

    summary(assessment.raw.fastq.counts$Total_count)

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##  180700  226100  264200  249900  275000  293000

Questions
---------

1.  Does the numbers reflect similar HiSeq / MiSeq runs? **MiSeq**

Investigating FastQC plots
--------------------------

Summary of FastQC reports are
[here](http://web.cbio.uct.ac.za/~gerrit/16Snodeassessment/assessment.run/qc/fastqc/fastqc_plots.htm)

### Questions

1.  Does the 52% GC content reflect microbial samples? **No completely
    random**
2.  Does the graphs show what is expected.

-   Differences in forward and reverse read qualities. ![optional
    caption text](figures/r1_qual.png) ![optional caption
    text](figures/r2_qual.png)
-   Is there anything to be worried about the per tile quality heatmap
    plot? ![optional caption
    text](figures/per_tile_sequence_quality.png)
-   A very mixed per base sequence content distribution. ![optional
    caption text](figures/per_base_sequence_content.png)
-   High duplication levels. ![optional caption
    text](figures/duplication_levels.png)
-   High levels of overrepresentation of sequences. ![optional caption
    text](figures/overrepressented_sequences.png)

1.  Read lengths are 300bp. Is this normal to expect form MiSeq runs?
    How should we set our filtering (done after merging) based on this.
2.  Which variable region does our reads hit? Does it make sense in
    terms of the sequence technology/platform used?

Investigating filtered/trimmed reads
====================================

    ##                 Samples_ID read_count
    ## 1  Cat11.merged.filtered_3     116366
    ## 2  Cat15.merged.filtered_3     110756
    ## 3  Cat20.merged.filtered_3     115317
    ## 4  Cat24.merged.filtered_3     128747
    ## 5  Cat29.merged.filtered_3     120693
    ## 6   Cat2.merged.filtered_3      88062
    ## 7  Cat33.merged.filtered_3     117888
    ## 8  Cat38.merged.filtered_3     114377
    ## 9  Cat42.merged.filtered_3     123856
    ## 10 Cat47.merged.filtered_3      94702
    ## 11 Cat51.merged.filtered_3     115170
    ## 12 Cat56.merged.filtered_3      90802
    ## 13 Cat60.merged.filtered_3      76637
    ## 14  Cat6.merged.filtered_3     107248

    summary(filtered_fastqs.counts$read_count)

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##   76640   97840  114800  108600  117500  128700

On average ~13% of reads are dropped after filtering (we can recheck
this)

    (124950-108600)/124950

    ## [1] 0.1308523

Investigating FastQC plots
--------------------------

Summary of FastQC reports on filtered/trimmed reads are
[here](http://web.cbio.uct.ac.za/~gerrit/16Snodeassessment/assessment.run/qc/fastqc.filtered_3/fastqc_plots.htm)

### Remarks

1.  We still have a 52% GC content reflect microbial samples.
2.  Does the graphs show what is expected.

-   Now we have high quality reads only. There is also nono low
    hanging tails. Forward and reverse reaeds are now merged. ![optional
    caption text](figures/after_filtering_and_trimming/qual.png)
-   We still have a verry mixed per base sequence content distribution.
    ![optional caption
    text](figures/after_filtering_and_trimming/per_base_sequence_content.png)
-   High duplication levels remains. ![optional caption
    text](figures/after_filtering_and_trimming/duplication_levels.png)
-   High levels of overrepresentation remains. ![optional caption
    text](figures/after_filtering_and_trimming/overrepressented_sequences.png)
