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
<code>
$ docker run -p 8888:8888 -e PORT=8888 -v "/var/www/image_resizer:/image_resizer  -it image_resizer
</code>.   



Remove all not used layers:    
<code>
$ docker system prune --volumes --all 
</code>.   


Remove dangling images:    
<code>
$ docker rmi $(docker images -f dangling=true -q)
</code>.   


Stop and remove all containers (running or not):    
<code>
docker rm $(docker stop $(docker ps -aq))
</code>.   


smtp server
$ docker run -it -p 2500:2500 -p 8080:8080 -p 8085:8085 --rm marcopas/docker-mailslurper

