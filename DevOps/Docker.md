**Docker commands**

1. Docker PS: To view list of running PODS.
2. Docker run <application-name> ( ex:hello-world ) - To run a docker container
3. Docker run -p(port mapping) 3000:80 hellow-world - To run a container in paticular port
4. Docker run -d(detaching the container) -p 3000:80 hellow-world - To detach and run a container in paticular port
5. Docker build -t <file Name>() <docker file directory>
6. Docker run -t(psedo terminal) -i(interactive mode) <file name> for [more refarance-](https://gist.github.com/v0lkan/c413cf9477b607db1ea1117c9de853df)

If docker not run in your windows ::powershell -ExecutionPolicy ByPass -File "C:\Program Files\Docker\Docker\resources\MobyLinux.ps1" -destroy
run this command

This command is for getting docker IP address
docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' container_name_or_id

docker container rm -f wildfly can be used to stop and remove the container in one command

[Docker most used commands](https://github.com/docker/labs/blob/master/developer-tools/java/chapters/ch04-run-container.adoc#stop-container)

[Few docker concepts](https://stackoverflow.com/questions/42545431/when-to-use-docker-compose-and-when-to-use-docker-swarm)


[Docker MySQL Commands](https://hub.docker.com/r/mysql/mysql-server/)


**Docker Postgres**

docker run -p 5432:5432 --name bp_backup -e POSTGRES_PASSWORD=mysecretpassword -d postgres

Show all existing container :
docker ps -a

