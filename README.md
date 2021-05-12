# JuliaCon2020-DataFrames-Tutorial

## Introduction

This tutorial is prepared for JuliaCon2020 presentation [A deep dive into
DataFrames.jl indexing](https://pretalx.com/juliacon2020/talk/8SFYHK/).

This version is updated to DataFrames.jl 1.1.1 release.

Its focus is on discussing all the details of indexing in DataFrames.jl. If you
are interested in introductory tutorials about how to use DataFrames.jl, please
check out the list [here](https://dataframes.juliadata.org/stable/)
and in general you might want to have a look at [my
blog](https://bkamins.github.io/) as most of the posts there are somehow related
to DataFrames.jl.

## Tutorial structure

The tutorial is split in two parts (there is going to be a short break between
them during the conference):

* Introductory: "by example" explanation of indexing and broadcasting
  rules in DataFrames.jl (file *indexing_part1_introduction.ipynb* if you want
  to do exercises by yourself or file
  *indexing_part1_introduction_solutions.ipynb* if you prefer just to see the
  solutions immediately).
* Advanced: detailed discussion how indexing in DataFrames.jl
  is actually implemented, and what are key design challenges
  (file: *indexing_part2_advanced.ipynb*).

## Preparing for running the tutorial

All the examples are prepared under Julia 1.6.1. If you use any other version of
Julia 1.x the examples should just work (if they do not please let me know via
an Issue). In such a case you should change the kernel in the Jupyter Notebook
to match the one Julia version you have installed.

Before you start please make sure that you have all the required packages
installed. The simplest way to do it is to perform the following steps
(I assume you have `git` and `julia` commands available):

1. Open a terminal in a directory where you want to have the tutorial to be
   stored.
2. Run `git clone https://github.com/bkamins/JuliaCon2020-DataFrames-Tutorial.git`
   to download the repository with the turorial (if you to not have `git`
   installed then you can download a Zip of this repository from GitHub and
   unpack it locally).
3. Run `cd JuliaCon2020-DataFrames-Tutorial` to switch a directory to the one
   where the tutorial has been downloaded.
4. On Kaggle go to
   https://www.kaggle.com/qks1lver/amex-nyse-nasdaq-stock-histories?select=fh_5yrs.csv
   and download the file *fh_5yrs.csv* (it is simplest to do it manually),
   after downloading it you will get a *75752_1304789_compressed_fh_5yrs.csv.zip*
   file (the name of the file might change so please check it), which you should
   unzip (a detailed instruction is OS dependent so I omit it here) and make
   sure that *fh_5yrs.csv* is in the same directory as the tutorial (if you
   followed my instructions the name of this directory is
   *JuliaCon2020-DataFrames-Tutorial*). In order to perform this step you
   need to be logged in to Kaggle. In case you have problem with this you can
   download the required file from
   http://bogumilkaminski.pl/files/juliacon2020_fh_5yrs.zip,
   but Kaggle access is preferred to give an appropriate recognition to the
   creator of the file (and download speed also should be better).
5. Run `julia --project=. -e "using Pkg; Pkg.instantiate(); Pkg.precompile()"`
   to make sure you have all the required packages automatically downloaded
   and precompiled (in case they would be missing; this step is optional and
   is recommended to be run only the first time you want to run the tutorial
   to make sure that all the packages are correctly set up before we start
   working with them)
6. Run `julia --project=. -e "using IJulia; notebook(dir=pwd())"` to start the
   Jupyter Notebook in the directory where the tutorials are store (note that
   in the terminal you do not see a prompt as the Julia process is running
   now).
7. Now you can work with the tutorials.
8. After you are done please make sure to choose "Quit" option in the top right
   hand side in the Jupyter Notebook. This will automatically terminate the
   Julia process in the terminal and prompt will reappear.

It is best if you have the above steps performed before joining the JuliaCon2020
presentation to make sure you can smoothly follow the tutorial.
