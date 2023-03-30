## WEEK 1
---
 This week we will cover basics with the following main points:
 - Docker
---
### DOCKER
- [x] Create our Dockerfile

A Dockerfile is the documents included all the commands so that Docker can know how to create image. In other words, Docker can build Docker image based on the commands on the Dockerfile.

#### What is Docker image and Docker container?
Think of **Docker image** as like a template, containing a set of instructions to build Docker container. **Docker container** is like a box where all of the dependencies and preconfigured elements as well as built applications are stored. It includes anything we need to run an applicaiton. 

Docker container is run isolated with other containers. Therefore, it is very convenience when we want to one specific image on other environment. The same Docker image means that the same instructions, same version, same dependencies. When it is used on other environment, it will limit th error and increase the reproducibility. 


