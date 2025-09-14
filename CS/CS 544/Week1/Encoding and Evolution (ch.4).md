# Lecture

## Dockerfile
?
- Have root privileges by default
```Dockerfile
FROM ..starting point
RUN .. during the build of an image
COPY
CMD .. default commands to run when running a new container
```
.
```Dockerfile
FROM ubuntu
RUN apt-get update && apt-get install unzip
```
- building image first time may take awhile, however building image second time doesn't since docker building caches