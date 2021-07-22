---
layout: default
title:  'FAQs'
---
{::options parse_block_html="true" /}

<style>
h1, .h1, h2, .h2, h3, .h3, h4, .h4 { margin-top: 50px }
p.caption {font-size: 0.9em;font-style: italic;color: grey;margin-right: 10%;margin-left: 10%;text-align: justify}
</style>

### <img border="0" src="https://www.svgrepo.com/show/7421/computer.svg" width="25" height="25"> Frequently asked questions

We recommend that you follow the pre-course installation instructions, which should avoid most bugs. As the tutorial is time limited, we will not be able to assist you in debugging your installations during the hands-on sessions.

**Questions within Docker containers**
<details>
  <summary markdown="span">`> docker: Got permission denied while trying to connect to the Docker ... connect: permission denied. See 'docker run --help'.`</summary>

  Make sure you are launching docker commands with `sudo`. For instance, `sudo docker run ...`
</details>

<details>
  <summary markdown="span">`> What is my username in the rstudio container?`</summary>

  Your user is `omics`. If this doesn't work for some reason, try `rstudio`.
</details>

<details>
  <summary markdown="span">`> WARNING: The requested image's platform ... does not match the detected host platform ... and no specific platform was requested 1e53..9509``</summary>

  You need to provide the correct platform in `docker run ... --platform [yourplatform] ...`. See [here](https://stackoverflow.com/a/68004485/1379826) for an example.
</details>

<details>
  <summary markdown="span">`> Can I use normal bash commands in the containers?`</summary>

  Yes, please use `sudo docker run -it ... bash` with any container. Note that you need to have `-it` to have an interactive tty.
</details>

<details>
  <summary markdown="span">`> How do I make the container see a folder in my own computer?`</summary>

  When you do `docker run ...`, map the folders. For instance, `docker run -v $(PWD):/omics/project/workshop/ ...` to map your working directory to the folder `/omics/project/workshop/` inside the container.
  
</details>

<details>
  <summary markdown="span">`> How do I make RStudio see the workshop contents?`</summary>

  From RStudio, please run `setwd('/project/')`, after which you can go to `File` and open the notebooks normally.
  
</details>

**Other questions**

<details>
  <summary markdown="span">`> I've installed everything through conda. Should I install instead the docker containers?`</summary>

  Yes, this is strongly recommended as it will avoid many bugs.
</details>

<details>
  <summary markdown="span">`> But I'd like to keep using conda. What are common ways to solve most bugs?`</summary>

Here are some helpful tips that may assist in solving installation problems or package-related bugs:  
- deactivate the environment if applicable;  
- clean cache with `conda clean -a -y`;  
- re-install the specific environment;  
- if the problem persists, consider installing the problematic package reported in the bug from terminal with `mamba install -c conda-forge [package name] --force-reinstall`. If you get an error `Problem: nothing provides requested [package name` please search for it [in anaconda cloud](https://anaconda.org/) and change the channel accordingly (e.g. one of `-c [bioconda | r | rdonnelly ]`);
- if the problem still persists, consider installing it manually within R from CRAN or bioconductor. You'll find all packages used at the end of each notebook and html file.
</details>

<details>
  <summary markdown="span">`> Command line developer tools not found (OSX)`</summary>

  If you don't yet have Mac OSX command line developer tools, please install it using:

  ```
  xcode-select --install
  ```
</details>


<details>  
  <summary markdown="span">`> rstudio crashes upon opening`</summary>  

  In terminal try to open R by typing: `r`. Examine the returned error.  
</details>

<details>
  <summary markdown="span">`> unable to load shared object '.../R/library/igraph/libs/igraph.dylib'`</summary>  

  In terminal, run  

  ```
  mamba install -c conda-forge igraph --force-reinstall
  ```
</details>

<details>
  <summary markdown="span">`> dyld: Library not loaded: @rpath/libncurses.6.dylib`</summary>  

  In terminal run  

  ```
  mamba install conda-forge::ncurses
  ```
</details>

<details>
  <summary markdown="span">`> mofapy package not found.`</summary>  

  Please install it from R with  

  ```
  library(reticulate)
  use_condaenv(condaenv='ismb_dr_ui_na')
  ```
</details>  

<details>
  <summary markdown="span">`> MOFA bugs`</summary>  

  Refer to [the MOFA repository](https://github.com/bioFAM/MOFA).  
</details>