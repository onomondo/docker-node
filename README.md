# docker-node

## How to add a new version

This example is from `13` to `14`

1. `$ cp -r 13 14`
2. Edit `14/Dockerfile` and change `13` to `14`
3. Edit `14/etc/apt/sources.list.d/nodesource.list` and change `13` to `14`
4. `$ docker build -t onomondo/node:14 -f 14/Dockerfile .`
5. `$ docker login`. Not needed if you're already logged in to docker.
6. `$ docker push onomondo/node:14`
