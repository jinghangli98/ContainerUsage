# ContainerUsage
## Docker
Docker is useful in that you do not need to install dependencies to run your application. Some useful commands to get started with docker can be illustrated with the following lines of codes:
```
docker pull wmhchallenge/pgs #pulling docker image
docker run -v $PWD:$PWD -w $PWD -it wmhchallenge/pgs #running docker image while mounting the current directory inside the docker image. The working directory inside the docker container is your current working directory
docker images ps #shows current running docker images
docker cp <container_id>:<container_path> <local_path> #copy a docker file to your local machine

```
However, one downside about docker is that, it might not have vim/nano pre-installed. 
## Singularity
```
singularity pull ~/pgs.sif docker://wmhchallenge/pgs #creating a singularity image from the dockerhub
singularity exec -B $PWD:$PWD -W $PWD ~/pgs.sif commands_inside_container #running singularity image while mounting the current directory inside the docker image. The working directory inside the docker container is your current working directory

sudo singularity build lolcow.sif docker://godlovedc/lolcow  # pulls and builds an example container

sudo singularity build --sandbox lolcow_sandbox/ lolcow.sif # converts from container to a writable sandbox

sudo singularity build lolcow2 lolcow_sandbox/ # converts from sandbox to container
```
