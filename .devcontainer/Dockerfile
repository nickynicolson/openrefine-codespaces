FROM ubuntu:22.04

WORKDIR /home/openrefine

RUN apt-get update -y
RUN apt-get install -y wget
RUN apt install default-jre
RUN wget -O openrefine.tar.gz https://github.com/OpenRefine/OpenRefine/releases/download/3.9.3/openrefine-linux-3.9.3.tar.gz 

RUN tar xzf openrefine.tar.gz 

# Create a directory we can save OpenRefine user project files into
RUN mkdir /mnt/refine
 
# Mount a Docker volume against that directory.
# This means we can save data to another volume and persist it
# if we get rid of the current container.
VOLUME /mnt/refine
 
#Expose the OpenRefine server port outside the container
EXPOSE 3333

CMD ['/home/openrefine/openrefine-3.9.3/refine']
