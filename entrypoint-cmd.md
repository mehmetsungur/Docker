# ENTRYPOINT - CMD 

- CMD and ENTRYPOINT work similarly, they execute a command at container runtime
- CMD can be overridden
- ENTRYPOINT is good to accept parameters

- Create this Dockerfile and build an image

```Dockerfile
FROM ubuntu
ENTRYPOINT ["sleep"]
```

- build the image 

```bash
docker build -t sleeper .
```

- run as a container and see the result

```bash
docker run sleeper
```

- you get the error saying that a parameter was missing

- run again this time with a parameter

```bash
docker run sleeper 5
```

- now you observe that the container waits 5 seconds to exit

- modify the Dockerfile adding CMD. here CMD is used to give a default value in case parameter is forgotten.

```Dockerfile
FROM ubuntu
ENTRYPOINT ["sleep"]
CMD ["1"]
```

=======
- a similar way can be applied on a sample node app file. here app.js is a default argument in case forgotten.

```Dockerfile
...
ENTRYPOINT ["node"]
CMD ["app.js"]
```
=======


- rebuild the image

```bash
docker build -t sleeper .
```

- run as a container

```bash
docker run sleeper
```
