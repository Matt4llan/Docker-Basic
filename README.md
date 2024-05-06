# Install Docker and create containers

## Objective

The objective of this tutorial is to guide me through the process of installing Docker and creating my first container on Linode's Cloud hosting platform.

### Skills Learned

By completing this lab, I will gain hands-on experience with Docker installation procedures and container creation, enabling me to incorporate containerization technology into my development workflow effectively.

### Tools Used

- Linode - Cloud Hosting Platform
- Solar Putty - To connect to the platform
- Docker - To create the containers

## What is Docker

Docker is an open-source platform that automates the deployment, scaling, and management of applications inside containers. Containers are lightweight, portable, and self-sufficient units that encapsulate the application code, runtime, system tools, libraries, and settings required to run the application. Docker provides a standardized way to package and distribute applications, allowing developers to build, ship, and run their applications seamlessly across different environments, from development to production. With Docker, developers can create isolated environments for their applications, ensuring consistency and reliability across various infrastructure platforms, whether it's on-premises, in the cloud, or hybrid environments.

## Step 1 - Creating and Installing Docker

To start will will create our Linode

![image](https://github.com/Matt4llan/Docker-Basic/assets/156334555/9a016270-3968-42ec-9f34-f2f1a2f36eb2)

Then select Docker from the marketplace

![image](https://github.com/Matt4llan/Docker-Basic/assets/156334555/1fec71bf-415d-4238-b222-4e5f194ec30c)

Image:  Ubuntu 22.04 LTS for stability and long term support
Region: London
Server: 2GB RAM, 1 CPU, 50GB Storage, 2TB Transfer
Label: docker-matt-basic
Setting a root password and clicking create.

![image](https://github.com/Matt4llan/Docker-Basic/assets/156334555/0a26caaf-72a2-47ea-a4e1-64b18e4a7afd)

## Step 2 - Connecting to the new image

![image](https://github.com/Matt4llan/Docker-Basic/assets/156334555/0fec12ea-e300-4746-8089-91107ca7e1d4)

## Step 3 - installing Docker
```
snap install docker
```

![image](https://github.com/Matt4llan/Docker-Basic/assets/156334555/e7349685-9bca-49c1-8276-88f5f3615566)

## Step 4 - Crating a Centos Docker container

Next im going to use the following commands to Install CENTOS into a docker container
```
docker pull centos
docker run -d -t --name dockercentos centos
docker ps
docker exec -it dockercentos bash
exit
```

- docker pull centos | This command downloads the CentOS image from Docker Hub to your local machine, making it available for use in creating containers.
- docker run -d -t --name dockercentos centos | This command creates a new container using the CentOS image. The container is named "dockercentos" and runs in the background.
  - -d | Detached mode, which means the container runs in the background
  - -t | Allocates a pseudo-TTY (terminal)
  - --name | Names the container
  - centos | Specifies the image to use for creating the container
- docker ps | This command displays information about the running containers on your system, including their container IDs, names, status, and other details. It confirms whether the container named "dockercentos" is running
- docker exec -it dockercentos bash | This command starts an interactive Bash shell session inside the "dockercentos" container, allowing you to directly interact with the CentOS environment running within the container
  - -it | Opens an interactive terminal session
  - docercentos | Specifies the name of the target container
  - bash | Specifies the command to execute inside the container (in this case, starting a Bash shell)
 
![image](https://github.com/Matt4llan/Docker-Basic/assets/156334555/93c03d68-c1fd-4805-b5d5-eab3067e0b13)

## Step 5 - Crating a Alpine Docker container

Next im going to use the following commands to Install Alpine into a docker container
```
docker pull alpine
docker run -d -t --name dockeralpine alpine
docker ps
docker exec -it dockeralpine sh
exit
```

![image](https://github.com/Matt4llan/Docker-Basic/assets/156334555/957e5907-38a9-4ed3-8ef8-2226f2740a46)

In the above we can see i tried to use the Bash shell to connect and it failed, this is likely that bash is not installed as Alpine is known for its lightweight nature, typically uses the "ash" shell instead of "bash" as its default shell.

Video of the above process | 'https://youtu.be/ef9156rysAY'

