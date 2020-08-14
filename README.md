# docker-node

## How to add a new version

This example is from `13` to `14`

1. `$ cp -r 13 14`
2. Edit `14/Dockerfile` and change `13` to `14`
3. Edit `14/etc/apt/sources.list.d/nodesource.list` and change `13` to `14`
4. `$ git add 14`
5. `$ git commit -m "Updated to node v14"`
6. `$ docker build -t onomondo/node:14 -f 14/Dockerfile .`
7. `$ docker login`. Not needed if you're already logged in to docker.
8. `$ docker push onomondo/node:14`
