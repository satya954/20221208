FROM python:3.9-slim
COPY . /srv/flask_app
WORKDIR /srv/flask_app
RUN apt-get clean && apt-get -y update
RUN DEBIAN_FRONTEND=noninteractive apt-get -y install apt-utils
RUN apt-get -y install nginx python3-dev build-essential
RUN pip install -r requirements.txt --src /usr/local/src
COPY nginx.conf /etc/nginx
RUN chmod +x ./start.sh
CMD ["./start.sh"]
