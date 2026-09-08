- Docker Image:
	- Everything needed to run a container.
	- A container image is a standardized package that includes all of the files, binaries, libraries, and configurations to run a container.


![[Pasted image 20251025151058.png]]
### How to write a Dockerfile?

0) Create a file called Dockerfile.
1) Define the base image used. This will be used as base to all project. 
2) Good practice but not mandatory. 
3) Copy the git content to the machine. 
4) Define the destination folder to the copy from Git.
5)  Run the node package for the app, the "> /dev/null" command is a redirection command and the destination is with get the log information. This extra part is the "extra to reduces the verbosity of the Docker build process".
6) Specify that containers from the build must use one specific port.
7) Specify which command will be run on the startup of the container. 

## Important Commands

- docker run -p 8000:8000 --name example1 todoapp = this command flags which port that will be used on the host machine. Therefore, making possible to navigate in the http://localhost:8000 to view the application. 
- docker images = return all images created 
	- Is good to know this command, because it helps to follow which was the last image created.
	
- docker ps -a = identify which containers have been started and removed.

- docker diff example = which files have been affected since the image was instantiated as a container.