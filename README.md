Investigating raw read counts
-----------------------------

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

    summary(assesment.raw.fastq.counts$Total_count)

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##  180700  226100  264200  249900  275000  293000

### Questions

1.  Does the numbers reflect similar HiSeq / MiSeq runs?

Investigating FastQC plots
--------------------------

Summary of FastQC reports are
[here](http://web.cbio.uct.ac.za/~gerrit/16Snodeassessment/assessment.run/qc/fastqc/fastqc_plots.htm)

### Questions

1.  Does the 52% GC content reflect microbial samples?
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
