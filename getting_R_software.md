# Running R on HPC systems (well, on CARC systems)

## Getting R in the first place

There are two options for accessing R at Carc and I will run through both approaches since there are pros and cons to each.
### Option 1
The first option is to activate an installed R module. When logged in to a CARC system you can use the `module avail` command to see which R versions are available. If you have a CARC account open a terminal and log in to follow along. 

```
yourusername@wheeler-sn$ module avail r-
```

which will print out the following (although I have truncated the output):

```
----------------------- /opt/spack/share/spack/modules/linux-centos7-x86_64 ------------------------
   ...
   r-3.4.1-gcc-4.8.5-python2-gzeg24m
   r-3.4.1-gcc-4.8.5-python2-zpkgqap
   r-3.4.1-intel-17.0.4-mkl-python2-67zsm3b
   r-3.4.1-intel-17.0.4-mkl-python2-gygkoab
   r-3.4.2-intel-18.0.2-python2-xsxuxwx
   r-3.4.3-gcc-4.8.5-python2-gk66fni
   r-3.4.3-gcc-4.8.5-python2-qv6gwz6
   r-3.4.3-gcc-6.1.0-python2-lyqiytq
   r-3.4.3-gcc-7.3.0-python2-zhxbajj
   r-3.4.3-intel-18.0.1-python2-3l4dkgz
   r-3.4.3-intel-18.0.1-python2-lr24ix6
   r-3.4.3-intel-18.0.2-python2-q3covk7
   r-3.5.0-gcc-4.8.5-python2-khqxja7
   r-3.5.0-gcc-7.3.0-python2-rvq3qk5
   r-3.5.0-intel-18.0.2-python2-mkl-r6lx6yy
   r-3.5.3-gcc-7.3.0-python2-ziiolp5
   r-3.6.0-gcc-4.8.5-python2-i4uimtp
   r-3.6.0-gcc-7.3.0-python2-7akol5t
   ...
Use "module spider" to find all possible modules.
Use "module keyword key1 key2 ..." to search for all possible modules matching any of the "keys".
```

These are all of the currently available R modules installed on Wheeler. In order to activate a R software module you use the `module load` command. For example:

```
yourusername@wheeler-sn$ module load r-3.6.0-gcc-7.3.0-python2-7akol5t
yourusername@wheeler-sn$ R

R version 3.6.0 (2019-04-26) -- "Planting of a Tree"
Copyright (C) 2019 The R Foundation for Statistical Computing
Platform: x86_64-pc-linux-gnu (64-bit)

R is free software and comes with ABSOLUTELY NO WARRANTY.
You are welcome to redistribute it under certain conditions.
Type 'license()' or 'licence()' for distribution details.

  Natural language support but running in an English locale

R is a collaborative project with many contributors.
Type 'contributors()' for more information and
'citation()' on how to cite R or R packages in publications.

Type 'demo()' for some demos, 'help()' for on-line help, or
'help.start()' for an HTML browser interface to help.
Type 'q()' to quit R.

> 
```

Will load R-3.6.0 that has been compiled with GCC-7.3.0. Normally you will be running R jobs in batch mode as oppposed to interactively, which means you will have the `module load` command in your PBS script, but we will get to that later. 
