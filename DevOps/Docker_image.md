Docker image inspect <IMAGE_NAME>:<IMAGE_TAG>


docker container run -itd alpine sh
Docker container get ephemeral storage to peroform its operation when we create a containe from image. UnionFs helps to mapped to the container in the read only mode.

docker container run -it myalpine alpine sh
This command helps to create new image from ephemeral storage.

docker container diff myalpine

docker container commit 

docker container push <REPO_NAME>/<IMAGE_NAME>:<IMAGE_TAG>
