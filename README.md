# Introduction

This code contains code to compare CSV files to Parquet files. I am interested in the storage requirements and the time needed for reading the file to memory.

## Set-up

I create tables contaning random numbers drawn from a Normal distribution with 0 mean and unit variance. I vary the number of rows and columns. For each table generated I save them as a save file and as a parquet file. For this step I do not use any compression on the parquet file.

To reduce the effect of the system, each file is read 500 times and the average is taken.

$$R = \frac{E[C]}{E[P]} $$

where $$E[C]$$ is the expected value of required time to read the CSV file to a dataframe and $$E[P]$$ is the expected value of the required time to read the Parquet file to a dataframe.


### Storage space

![Disk space ratio of Parquetto CSV](figs/size_ratio.png?raw=true "Size ratio of the same data stored as CSV file vs Parquet")


### Reading time

![Read time  ratio of CSV to Parquet](figs/time_ratio.png?raw=true "Size ratio of the same data stored as CSV file vs Parquet")