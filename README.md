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

#EXPOSE 8888
#docker run -p 8888:8888 -e PORT=8888 -v "/var/www/image_resizer:/image_resizer  -it image_resizer
# docker run -p 8888:8888 -e PORT=8888  -v /var/www/image_resizer:/image_resizer  -it image_resizer
