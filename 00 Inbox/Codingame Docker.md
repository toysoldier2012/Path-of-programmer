
# QCM

### Docker storage: Best practice
Language knowledge (40 pts)

Which of the following statements would you qualify as a best practice regarding the management of data for a dockerized application?

_Multiple answers expected_

- Try to store application data in the container’s writable layer using a **storage driver**
- Try to use **bind** mounts instead of using **volume** mounts
- Use a **secrets** mount for sensitive data such as passwords
- Use a **tmpfs** mount if your application produces a lot of non-persistent data

### Docker inspect: Getting network information
Language knowledge (40 pts)

Consider the following docker inspect output:  

```json
$docker inspect mycontainer
[
{
    "Id":
"c9e23ca73a66365acc8d42714d4aae22c5e1dfc0dc079ad4366eb8dba8336f86",
    "Created": "2015-08-05T16:18:09.306673609Z",
    "Path": "/apps",
    "Args": [],
    "State": {
        "Running": true,
        "Paused": false,
        "Restarting": false,
        "OOMKilled": false,
        "Dead": false,
        "Pid": 3053,
        "ExitCode": 0,
        "Error": "",
        "StartedAt": "2018-10-09T16:18:09.374896026Z",
        "FinishedAt": "0001-01-01T00:00:00Z"
    },
    "Image":
"f76c0f6b907fd796e744f0def3557b5126239a48f0979bdba4b838b6d711ebeb",
    "NetworkSettings": {
        "Bridge": "",
        "EndpointID":
"bf2db906cf18b35540c110653200e52c00f8f42b9709bd6095037abb993ec179",
        "Gateway": "172.17.42.1",
        "GlobalIPv6Address": "",
        "GlobalIPv6PrefixLen": 0,
        "HairpinMode": false,
        "IPAddress": "172.17.0.3",
        "IPPrefixLen": 16,
        "IPv6Gateway": "",
        "LinkLocalIPv6Address": "",
        "LinkLocalIPv6PrefixLen": 0,
        "MacAddress": "02:42:ac:11:00:03",
        "NetworkID":
"34cd76d0b7493bb5a11045efc0bae93e289e45d9a47fb075eaf567598d7c4a6b",
        "PortMapping": null,
        "Ports": {},
        "SandboxKey": "/var/run/docker/netns/c9e23ca73a66",
        "SecondaryIPAddresses": null,
        "SecondaryIPv6Addresses": null
    },
    
    ...
    
    Output is truncated
```

Which command can you run to specifically return **only** `ipaddress` of the container `mycontainer`**?**

- `docker inspect -f '{{.NetworkSettings.IPAddress}}' mycontainer`
- `docker inspect mycontainer -o '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}'`
- `docker inspect -f '{{NetworkSettings(IPAddress)}' mycontainer`
- `docker inspect -o '{{mycontainer.NetworkSettings.IPAddress}}'`

### Docker swarm: Getting service logs
Problem solving (40 pts)

A user reported that a docker swarm service `billing-manager` has stopped working properly.

Your cluster is still using the **default logging drivers**.

Which command should you use to **gather information** for troubleshooting purposes?

- `docker service logs billing-manager`
- `docker logs billing-manager`
- `docker container logs billing-manager`
- `docker swarm logs billing-manager`

### Docker build: Using .dockerignore
Design (40 pts)

To increase docker build’s efficiency and performance you would like to **exclude irrelevant files and directories** from the context directory.

What should you do?

- Use option "`docker build -e <irrelevant files/dir>`" when building
- Add a `.gitexclude` file in the context folder to specify the irrelevant files/dirs
- Add a `.dockerignore` file in the context folder to specify the irrelevant files/dirs
- Use an "`EXCLUDE  <irrelevant files/dir>`" instruction inside your dockerfile

### Docker image: Building image
Language knowledge (20 pts)

Which command will **build** a docker image with the name `webportal` and tag `1.0` using the Dockerfile available in the current directory?

- `docker build -t webportal:1.0 .`
- `docker build webportal:1.0 -f .`
- `docker build . --name=webportal:1.0`
- `docker build webportal -t 1.0 .`

### Docker registry: Login to server
Language knowledge (20 pts)

What command can be used to **log in** to the docker registry **"docker-registry.company.com"** using user **"jerry"**?

- `docker login --username=jerry --serverurl=docker-registry.company.com`
- `docker login --username=jerry docker-registry.company.com`
- `docker login -u jerry -h docker-registry.company.com`
- `docker login jerry docker-registry.company.com`

### Container policy: Managing restart policy
Design (40 pts)

You want to run a new container.

You want the docker daemon to try to restart the container indefinitely and also always restart the container on startup of the daemon, regardless of the current state of the container.

Which **restart policy** is best for you?

- on-failure
- unless-stopped
- always
- no
- startup

### Docker network: Using custom dns server
Language knowledge (40 pts)

Which of the following commands will create a container with custom DNS server "8.8.8.8"?

- docker container create --dns=8.8.8.8
- docker container create --custom-dns=8.8.8.8
- docker container create --add-dns=8.8.8.8
- docker container create --resolve=8.8.8.8

### Dockerfile: Choosing between CMD and ENTRYPOINT
Design (20 pts)

Are there any differences between **CMD** and **ENTRYPOINT** instructions in Dockerfile?

- There's no difference. It's only an alias
- Yes, the **CMD** instruction allows you to set a default command, which will be executed only when you run a container without specifying a command, while the **ENTRYPOINT** argument will always be executed
- Yes, **ENTRYPOINT** must always be used in conjuction with **CMD**, while **CMD** can be used by itself
- Yes, **ENTRYPOINT** is used to specify the default directory to run the task specified in **CMD**

### Docker container: Running interactive shell
Language knowledge (20 pts)

To investigate a new issue, you need to run an **interactive shell (bash)** on a running container named `mycontainer` to be able to execute commands from **inside the running container.**

Which command will allow you to do that?

- `docker run -it mycontainer /bin/bash`
- `docker ssh mycontainer`
- `docker exec -d mycontainer --interactive /bin/bash`
- `docker exec -it mycontainer /bin/bash`

### Dockerfile: EXPOSE
Language knowledge (20 pts)

What will happen if you use the `EXPOSE` instruction in a Dockerfile?

- It will instruct the Docker daemon that the container will listen on a specified port at runtime
- It will instruct the Docker daemon that a specified directory in the container will be exposed to the host at runtime
- It will instruct the Docker daemon to listen on all ports
- There is no such thing as an `EXPOSE` instruction for Dockerfiles
- It will instruct the Docker daemon to route all network traffic from container to host through NAT

### Docker image: Pulling image
Language knowledge (20 pts)

You need the image `nginx` with tag `latest` to be available on your local docker storage. You decide to get this image from a default public repository.

Which command should you use?

- `docker pull nginx:latest`
- `docker push nginx:latest`
- `docker get nginx:latest`
- `docker download nginx:latest`

















