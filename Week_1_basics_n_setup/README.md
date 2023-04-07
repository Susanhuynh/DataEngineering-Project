# WEEK 1
---
 This week we will cover basics with the following main points:
 - Docker

## DOCKER
---
- [x] Create our Dockerfile

A Dockerfile is the documents included all the commands so that Docker can know how to create image. In other words, Docker can build Docker image based on the commands on the Dockerfile.

> ### What is Docker image and Docker container?
> Think of **Docker image** as like a template, containing a set of instructions to build Docker container. **Docker container** is like a box where all of the dependencies and preconfigured elements as well as built applications are stored. It includes anything we need to run an applicaiton. 
>
> Docker container is run isolated with other containers. Therefore, it is very convenience when we want to one specific image on other environment. The same Docker image means that the same instructions, same version, same dependencies. When it is used on other environment, it will limit th error and increase the reproducibility. 

- [x] Create pipeline.py

Create pipeline.py and download sys library....

- [x] Install pgcli - Command Line Interface for Postgres
Install Command Line Interface for Postgress. It is a Python library. Because we put our database in Postgres therefore we need to use cli for Postgres to access our database. 
- [x] Run Progres image and create new empty database

Next, we run Postgres image by the code below in order that Docker will create container with Postgres environment where we can upload our NY TAXI database there. 

The first part `docker run -it` to create the image. If we dont have that image ready in the host machine, docker will pull it from registry and create image we want. `-e` is used to set evironmental variable when run docker with `docker run`.Because docker is stateless so next time when we run postgress, out database will not be there. Therefore, we need to make sure that our database is still there by mapping the folder we have in our host machine to folder in host machine. This is called `mounting` and we use `-v` and mapping. 

        docker run -it  
         -e POSTGRES_USER="root" \  
         -e POSTGRES_PASSWORD="root" \  
         -e POSTGRES_DB="ny_taxi" \  
         -v $(pwd)/ny_taxi_postgres_data:/var/lib/postgresql/data \  
         -p 5432:5432 \  
        postgres:13

`-e POSTGRES_USER="root"`: The name of our PostgreSQL user.  
`-e POSTGRES_PASSWORD="root"`: Password of our PostgreSQL user.  
`-e POSTGRES_DB="ny_taxi"`: Name of our database.  

- [x] Access new database by progres through pgcli
`pgcli -h localhost -p 5432 -u root -d ny_taxi`

- [] Load CSV data file to our new database on Postgres by Jupyter Notebook

