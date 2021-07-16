---
layout: default
title:  Pre-course
---

{::options parse_block_html="true" /}

#### <img border="0" src="https://www.svgrepo.com/show/26916/book.svg" width="15" height="15"> Preparation for the tutorial  
***

This workshop will comprise both lectures and hands-on exercises. While you will be able to follow all exercises from the html files, we recommend that you prepare by 1. [familiarizing yourself with basic R and Python](#-programming-with-r-and-python), 2. [installing the containers](#-docker-instructions), and 3. **going through the following 3 notebooks**. If you want to run them in your system please see the [labs page](./labs.html) for setup instructions.  
- [Data pre-processing notebook](./session_preparation/data_preparation/preprocessing.ipynb) ([html](./session_preparation/data_preparation/preprocessing.html))
- [Dimesionality reduction](./session_preparation/dimreduction/OmicsIntegration_DimensionReduction.Rmd) ([html](./session_preparation/dimreduction/OmicsIntegration_DimensionReduction.html))
- [Feature selection notebook](./session_preparation/feature_selection/OmicsIntegration_FeatureSelection.Rmd) ([html](./session_preparation/feature_selection/OmicsIntegration_FeatureSelection.html))

If you are interested you can go through the [additional reading materials][5].

#### <img border="0" src="https://www.svgrepo.com/show/7421/computer.svg" width="25" height="25"> Programming with R and Python  
***

The course will be taught using both R and Python depending on the tools available. While you will be able to follow all lectures and exercises conceptually, it is helpful if you are familiar with basic usage of both programming languages:  
- [R (part_1)](https://swcarpentry.github.io/r-novice-inflammation/)
- [R (part_2)](http://swcarpentry.github.io/r-novice-gapminder/)
- [Python (part_1)](https://swcarpentry.github.io/python-novice-inflammation/)
- [Python (part_2)](http://swcarpentry.github.io/python-novice-gapminder/)

You should also be familiar with basic command line input (`mkdir`, `cd`, `ls`, `cp`, `mv`).

#### <img border="0" src="https://www.svgrepo.com/show/303231/docker-logo.svg" width="25" height="25"> Docker instructions  
***

To reproduce all analyses you will need to:  
- [Install Docker](https://docs.docker.com/get-docker/);  
- [Create the containers](#create-the-containers);  
- [Launch rstudio or jupyter](#launch-rstudio-or-jupyter);  
- [Stop the containers](#stop-the-containers)

If you have previously followed the [conda instructions](conda_instructions.md), we still recommend that you follow the instructions below as they may avoid some bugs.

##### Create the containers

At this point you need to create the two containers for all Rstudio or Jupyter notebooks. You can do so by choosing one of the following options

either [1. Downloading the image from Dockerhub](#download-image-from-dockerhub) or [2. Download the Dockerfiles and build the images].

<details>
  <summary markdown="span">**Download image from Dockerhub** (recommended)</summary>

  Pull and start the images
  ```
  ########### Rstudio image ###########
  # Your user is 'omics' (without the quotes)
  # Replace <yourpassword> with your desired password
  docker run -d -p 8787:8787 -e PASSWORD=<yourpassword> ruibenfeitas/rstudio:16_07_2021

  ########### Jupyter image ###########
  # Your user is 'jovyan' (without the quotes)
  # Replace <yourpassword> with your desired password
  docker run ruibenfeitas/jupyter:16_07_2021
  ```

</details>


<details>
  <summary markdown="span">**Download the dockerfiles from github**</summary>

On github you will find the dockerfiles necessary [here](./docker). Download all files, [install docker compose](https://docs.docker.com/compose/install/) and then run:

```
docker-compose build
```

At this point you need to start and execute the container commands:  

```
########### Rstudio image ###########
# Your user is 'omics' (without the quotes)
# Replace <yourpassword> with your desired password
docker-compose up -d -p 8787:8787 -e PASSWORD=<yourpassword> -e JUPYTER_TOKEN=<yourpassword>

########### Jupyter image ###########
# Your user is 'jovyan' (without the quotes)
# Replace <yourpassword> with your desired password
docker-compose up -d -p 8888:8888 -e JUPYTER_TOKEN=<yourpassword>
```

</details>



##### Launch RStudio or Jupyter

Ensure you have followed all the instructions above and that your containers are running. If you have followed the instructions from the recommended solution you can simply access either RStudio or Jupyter from your browser with:
- `localhost:8888` to launch jupyter
- `localhost:8787` to launch rstudio

If you want to verify that your containers are running use `docker ps`.

##### Stop the containers
To stop the containers write `docker stop [container name]`.


[2]: https://datacarpentry.org/genomics-r-intro/
[3]: https://datacarpentry.org/python-ecology-lesson/
[4]: https://nbisweden.github.io/workshop-python/ht19/
[5]: reading_materials.md
[6]: https://nbisweden.github.io/workshop-r/