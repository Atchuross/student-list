# Python Flask API Dockerfile
FROM python:3.8-buster

LABEL maintainer="CLAUZEL Clément"

WORKDIR /

COPY requirements.txt .
RUN apt update -y && apt install python-dev python3-dev libsasl2-dev python-dev libldap2-dev libssl-dev -y
RUN pip3 install -r /requirements.txt

RUN mkdir /data
VOLUME /data

COPY . .

EXPOSE 5000

CMD [ "python3", "./student_age.py" ]


#docker build -t simple_api .
#docker run --name simple_api -d -p 5000:5000 -v /home/vagrant/data:/data simple_api