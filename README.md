# Optimal control of laser pulse spot welding

Authors:

## Initial cloning
* Clone this repository using either
  ```bash
  git clone --recurse-submodules git@gitlab.hrz.tu-chemnitz.de:numapde/Publications/optimal-control-spot-welding.git 
  ```
  if you have placed an SSH key in https://gitlab.hrz.tu-chemnitz.de/profile/keys (the preferred method), or else
  ```bash
  git clone --recurse-submodules https://gitlab.hrz.tu-chemnitz.de/numapde/Publications/optimal-control-spot-welding.git 
  ```
* Then run 
  ```bash
  bin/numapde-submodules-update.sh
  ```
  to update the submodules numapde-public/numapde-latex> and numapde-public/numapde-bibliography>.

## LaTeX
* The file `numapde-bibliography/numapde.bib` should be your primary source of references.
Additional references should be added to `numapde-local.bib`.
* Please use commands as documented in https://gitlab.hrz.tu-chemnitz.de/numapde-public/numapde-latex/raw/master/numapde-latex-documentation.pdf?inline=false.
For instance, write $`\|\mathcal{A}\|`$ as `\norm{\cA}` and not as `\|\mathcal{A}\|`.
* Declare additional commands as necessary in `numapde-local.sty`.
Additional packages should also be loaded there.

## Preprint and journal versions
Initially the repository contains the following files: 
* `manuscript-numapde-preprint.tex` is an auto-generated master file which serves to typeset the manuscript in the `numapde-preprint.cls` framework. Do not edit this file.
* `main.tex` contains the main body of the manuscript, both for preprint and journal versions.
* `manuscript.yaml` contains meta data for your manuscript, including authors, title, abstract and much more. Edit this as necessary.
* `numapde-local.sty` should be used to load additional packages, define additional commands etc.
* `numapde-local.bib` should be used to include new bibliographic entries specific to this publication. The idea is that these be eventually merged in `numapde-bibliography/numapde.bib`.

After updating `manuscript.yaml` (or any time you like) you can run
```bash
numapde-prepare-manuscript.py
```
to re-create or update the master file `manuscript-numapde-preprint.tex` for the preprint version.
This should be the framework in which the manuscript is developed.

At any time, you can create additional master files for journal versions, e.g., using 
```bash
numapde-prepare-manuscript.py --journal sicon
```
This will create `manuscript-sicon.tex` as well as the legacy BibTeX file `manuscript-sicon.bib` containing the references found in `manuscript-numapde-preprint.bcf` at the time the command is issued. 

If you like, you may rename `main.tex` `manuscript.yaml` and also use an output prefix different from `manuscript-`.
In this case, you will have to call `numapde-preprare-manuscript.py` with additional arguments, see `numapde-preprare-manuscript.py --help`.

## Daily workflow
* Run 
  ```bash
  bin/numapde-submodules-update.sh
  ```
  regularly to update the submodules.
* Run
  ```bash
  bin/numapde-pack-it-all.sh --help
  ```
  to learn about the script and its options which will pack the main `.tex` file and its depenencies into a `.zip` file, e.g., for submission to https://arxiv.org and to provide the source files of an accepted journal version.
  

## Artifacts

The latest automatically built artifact `manuscript-numapde-preprint.pdf` can be viewed [here](https://gitlab.hrz.tu-chemnitz.de/numapde/Publications/optimal-control-spot-welding/-/jobs/artifacts/master/file/manuscript-numapde-preprint.pdf?job=tex) or downloaded via this [direct link](https://gitlab.hrz.tu-chemnitz.de/numapde/Publications/optimal-control-spot-welding/-/jobs/artifacts/master/raw/manuscript-numapde-preprint.pdf?job=tex).
