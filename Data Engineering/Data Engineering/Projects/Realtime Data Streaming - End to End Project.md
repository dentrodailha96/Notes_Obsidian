
- Reproduction of this project: https://www.youtube.com/watch?v=GqAcTrqKcrY

## Docker

Docker definition: [https://aws.plainenglish.io/docker-explained-simply-for-a-10-year-old-the-magic-box-for-computer-programs-94452b930d6b](https://aws.plainenglish.io/docker-explained-simply-for-a-10-year-old-the-magic-box-for-computer-programs-94452b930d6b)

- Docker Compose: 
	- Uses an YAML file to organize the multi-container.
	- Ensures that each service runs in its own container, avoiding conflicts.
	- Orchestrates the services of the container. In another words, defines the dependencies between each service. 
	- docker compose up = creates and starts all your services. 
	- docker compose run = focuses on individual services. It starts a specified service along with its dependencies, allowing to run tests or perform one-off tasks within that container.

- Docker Image:
	- Everything needed to run a container.
	- A container image is a standardized package that includes all of the files, binaries, libraries, and configurations to run a container.


## Airflow
