# Docker Recipes

## Run already built docker image

 Build a docker image with tag docker_fluentd
```
docker build  -t docker_fluentd .
```
### Run a simple image in your terminal
```
 docker container run -it --rm --entrypoint /bin/bash docker_fluentd 
```
* --entrypoint - Overwrite the default ENTRYPOINT of the image, hear demands to use /bin/bash
* -it - Keep STDIN open even if not attached
* --rm - Automatically remove the container when it exits

### Run a image where you have to mount aws configuration and specify a region in environment variable
```
 docker container run --env REGION=eu-central-1 -it --rm --entrypoint /bin/bash -v ~/.aws:/home/fluent/.aws docker_fluentd 
```
* -v ~/.aws:/home/fluent/.aws - mount .aws from your home directory to /home/fluent/.aws in the image
* --env REGION=eu-central-1 - create an environment variable

