FROM alpine:3.11.5

RUN apk add --no-cache python3-dev \
    && pip3 install --upgrade pip

EXPOSE 4700
RUN mkdir -p /usr/src/app

WORKDIR /usr/src/app

COPY requirements.txt /usr/src/app

RUN pip3 --no-cache-dir install -r requirements.txt

COPY . /usr/src/app

CMD ["python3", "app.py"]


FROM jenkins/jenkins:lts-jdk11
USER root
RUN apt-get update
RUN apt-get install -y python3-pip
# Install app dependencies
RUN pip install --upgrade pip
