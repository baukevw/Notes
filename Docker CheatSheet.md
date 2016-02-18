## Docker Cheatsheet

Start the docker machine
```bash
docker-machine start
```

Setup the console
```bash
eval $(docker-machine env)
```

List all containers
```bash
docker ps -a
```

Build a project (Dockerfile required)
```bash
docker build .
```

Run a container
```bash
docker run --name NAME -p OUTSIDEPORT:INSIDEPORT -d IMAGE_ID
```

Link a container
```bash
docker run --name NAME -p OUTSIDEPORT:INSIDEPORT --link LINK_TO-NAME -d IMAGE_ID
```
