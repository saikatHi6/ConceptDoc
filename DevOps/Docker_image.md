Docker image inspect <IMAGE_NAME>:<IMAGE_TAG>


docker container run -itd alpine sh
Docker container get ephemeral storage to peroform its operation when we create a containe from image. UnionFs helps to mapped to the container in the read only mode.

docker container run -it myalpine alpine sh
This command helps to create new image from ephemeral storage.

docker container diff myalpine

docker container commit <CONTAINER_NAME>
Help us to create an on-disk copy of ephemeral storage from a container.

docker image push <REPO_NAME>/<IMAGE_NAME>:<IMAGE_TAG>


## Docker Commands
<b> Build Time Instruction </b>

1) RUN: Which helps to run on the container created in each build steps.
2) EXPOSE: we can mentioned open port which will help to connect over the network.
3) ENV: Help to set envrionment variable inside the container.
4) COPY: copy the content to the resulting image.
5) VOLUME: We can create mount point and then mount external storage to it.
6) HEALTHCHECK : We can define readiness and liveliness of the container started by the given image.
7) SHELL : We can define default shell for the commands which run as shell form.

<b> Run Time Instruction </b>

1) CMD: It provides default to the container created by the image
2) ENTRYPOINT: Make the container like executable. 
