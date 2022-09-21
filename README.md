# docker
# Example for creaiting Dockerfile

FROM python:2


#VOLUME ["/var/www/image_resizer", "/image_resizer"]

#ENV PATH=$PATH:/image_resizer
#ENV PYTHONPATH /image_resizer
ENV DIRPATH /image_resizer

WORKDIR /image_resizer
RUN pwd

#COPY ./image_resizer/ ./
#ADD ./image_resizer/ ./

RUN pip install Wand

CMD ["python", "./serverThread.py" ]

Run docker: 
- p - port onlocal:incontainer
- e - envonments
- v - volume(folder on local:folder in container)

docker run -p 8888:8888 -e PORT=8888 -v "/var/www/image_resizer:/image_resizer  -it image_resizer

Remove all not used layers

$ docker system prune --volumes --all 

Remove dangling images

{code}
$ docker rmi $(docker images -f dangling=true -q)
{code}

docker rm $(docker stop $(docker ps -aq))
