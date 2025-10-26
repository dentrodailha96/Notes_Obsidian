
Docker definition: [https://aws.plainenglish.io/docker-explained-simply-for-a-10-year-old-the-magic-box-for-computer-programs-94452b930d6b](https://aws.plainenglish.io/docker-explained-simply-for-a-10-year-old-the-magic-box-for-computer-programs-94452b930d6b)

Book: Docker in Practice

## Basic Concepts

Docker is a command-line program that you run. Basically, it is containers that run systems defined by Images and these images are combination of layers and metadata. 

![[Pasted image 20251025145455.png]]

#### Main Commands

![[Pasted image 20251025145721.png]]
- docker build . (the dot represents the path of the Dockerfile file)
- [[https://docs.docker.com/reference/cli/docker/compose/up/ | docker compose up -d]] = build, (re)creates, starts and attaches to containers for a service. 

### Key Concepts

- Images: Collection of filesystem layers and some metadata. Equivalent of a "class".
- Layers: Collection of changes to files, keep the history of changes, similar to a Git.
- Containers: it runs the image instance, objects. 

![[Pasted image 20251025150012.png]]
