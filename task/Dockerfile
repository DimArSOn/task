FROM macpaw/internship
MAINTAINER muha.dimaa@gmail.com

RUN  apt-get update && apt-get install -y apt-utils logrotate zip unzip vim nano
RUN apt-get install -y python-dev python-pip
RUN mkdir -p /etc/logrotate.d /etc/init
ADD /app/main.py /app/main.py 
ADD /app/nginx.conf /etc/nginx.conf
CMD ["/usr/sbin/nginx"]
RUN pip install virtualenv
RUN mkdir -p /app/my_app
RUN cd /app/
RUN virtualenv /app/my_app_venv
RUN . /app/my_app_venv/bin/activate
RUN pip install uwsgi
RUN uwsgi --socket 127.0.0.1:8080 --protocol=http -w main


EXPOSE 80 8080