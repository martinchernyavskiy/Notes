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
RUN apt-get update && apt-get install -y unzip python3-pip
RUN pip3 install pandas --break-system-packages

COPY hello.py /hello.py 
CMD ["python3", "/hello.py"]
```
- building image first time may take awhile, however building image second time doesn't since docker building caches various layers

## Networking

