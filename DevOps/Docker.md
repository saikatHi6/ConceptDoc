**Docker commands**

1. Docker PS: To view list of running PODS.
2. Docker run <application-name> ( ex:hello-world ) - To run a docker container
3. Docker run -p(port mapping) 3000:80 hellow-world - To run a container in paticular port
4. Docker run -d(detaching the container) -p 3000:80 hellow-world - To detach and run a container in paticular port
5. Docker build -t <file Name>() <docker file directory>
6. Docker run -t(psedo terminal) -i(interactive mode) <file name> for [more refarance-](https://gist.github.com/v0lkan/c413cf9477b607db1ea1117c9de853df)

If docker not run in your windows ::powershell -ExecutionPolicy ByPass -File "C:\Program Files\Docker\Docker\resources\MobyLinux.ps1" -destroy
run this command
