---
title: "Verificarlo: Monday"
date: 2022-11-09
draft: false
---


## Schedule Monday 21st November

* 09:00 - 9:40 : Verificarlo - a tool for debugging and assessing floating point precision and reproducibility. _Pablo de Oliveira Castro_
* 10:00 - 12:00 : Verificarlo Tutorial (practical session)
* 12:00 - 13:00 : Lunch on site
* 13:00 - 13:20 : Mixed-precision exploration on Cornell-Holland Ab-initio Materials Package. _François Coppens_.
* 13:20 - 13:40 : Demonstration Verificarlo-CI in the TREX project. _Aurelien Delval_
* 13:40 - 17:00 : Hands-on session on participant's codes

## Verificarlo Tutorial

This tutorial demonstrates how to use Verificarlo to study and improve the numerical accuracy of programs.

## Instructions for running the tutorial in CALMIP

1. Login into `olympe`
2. Add the following to your `.bashrc` to export the path to TREX modulefiles:
```
export MODULEPATH=${MODULEPATH}:/usr/local/trex/modulefiles
```

2. Retrieve and untar the sources for the tutorial with:
```
wget https://github.com/verificarlo/verificarlo_tutorial/files/9840599/verificarlo-tutorial.tar.gz
tar xzvf verificarlo-tutorial.tar.gz
```

3. Allocate a computing node with
```
$ salloc --nodes=1 --time=2:00:00
salloc: Granted job allocation 961958
salloc: Waiting for resource configuration
salloc: Nodes olympecomp358 are ready for job
```
4. Log into the allocated node
```
$ ssh olympecomp358 # replace with the name of your node
```

5. Load the verificarlo module
```
$ module load verificarlo/0.9.1
```
5. Start verificarlo singularity image and move into the tutorial working directory:
```
$ sing-verificarlo
Singularity verificarlo-v0.9.1.sif:~> cd verificarlo-tutorial/
Singularity verificarlo-v0.9.1.sif:~/verificarlo-tutorial> 
```

The singularity image will automatically mount the host's local directory. We
recommend that you use two terminals, one outside of the image to edit files;
one inside the image to run the commands.

You can also work locally to edit files and view generated plots by mouting the remote directory with `mkdir calmip-wd && sshfs olympe: calmip-wd/`.

You are now ready to start the verificarlo tutorial. The instructions are
available in the pdf below. You can ignore the docker commands in section 1, since you are
already running inside the verificarlo singularity container and directly jump to section 2.

(If you want to work on your own laptop, you can instead use the docker commands in section 1.)

## Ressources

* [Tutorial handout in English (verificarlo-tutorial.pdf)](https://github.com/verificarlo/verificarlo_tutorial/files/9840629/verificarlo-tutorial.pdf)
* [Tutorial sources (verificarlo-tutorial.tar.gz)](https://github.com/verificarlo/verificarlo_tutorial/files/9840599/verificarlo-tutorial.tar.gz)
