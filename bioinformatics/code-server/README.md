# Usage
By default, the docker-compose.yml builds the clariy001/bioinformatics:code-server image which itself is an extension of clarity001/bioinformatics:base.

To add you own dependencies, make a separate dockerfile that is built upon clarity001/binformatics:base. Push that dockerfile to docker.io, then use that as the base image for the dockerfile in the this directory (i.e. replace FROM clarity001/bioinformatics:base) with your docker image (e.g. FROM dockerusername/mydockerimage:tag).

Lastly, uncomment 'build: .' and comment out 'image: clariy001/bioinformatics:code-server'. This will cause docker compose to build the image specified by the dockerfile in the working directory. You may need to manually remove the old image using 'docker rmi imagename'.
