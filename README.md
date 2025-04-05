<!-- Copyright 2025 Kieran W Harvie. All rights reserved. --> 

:wave: Hi, this repository is a backup of my math notes.

It is split into projects and  structured such that each project has its own tex files in the home directory and possibly an accompanying bib file or subdirectory.

| tex File | Description |
| --- | --- |
| miscellaneous | The main and most active project where miscellaneous sections are simply added as they are finished. |
| fourier | The first project on the Fourier transform. Largely sunsetted. |
| asymmetric_cryptography | Describing some asymmetric cryptosystems using modular arithmetic. |
| neural-network | Analysis of a toy model of a neural network using incidence algebra. |
| blossom_theory | Meant to be the application of blossoms to Bézier geometry, currently suffering from some scope creep. |
| common_preamble | A file containing a bunch utility declarations shared between the other tex files. |

:warning: These notes haven't gone through any real peer-review. Only a fool would apply any result found here without conducting additional research. :warning:

# Build Guide
The core files are given in vanilla LaTeX and BibTeX and can likely be built using whatever LaTeX pipeline you prefer.

To achieve a full build I use `pdflatex` once,
then `biber` once,
then `pdflatex` twice:
```sh
pdflatex blossom_theory #Create citation information for biber.
biber blossom_theory #Create bibliography information for pdflatex.
pdflatex blossom_theory #Create structure and reference information for pdflatex.
pdflatex blossom_theory #Create the pdf file.
```
And my versions of these tools are:
```
biber version: 2.19
pdfTeX 3.141592653-2.6-1.40.25 (TeX Live 2023)
```
Note that for a partial build you only need to use commands as far back as the change from the previous build is.
So if there's only structural changes but no citation or bibliography changes you can get away with only using `pdflatex` twice.
