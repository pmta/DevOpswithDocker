FROM ubuntu:18.04

ENV LC_ALL=C.UTF-8 
RUN apt-get update && apt-get install -y wget python-pip && \
    pip install yle-dl && mkdir /downloads && \
    apt-get clean && apt-get purge -y --auto-remove python-pip && \
    apt-get install -y python python-setuptools python-six python-idna && \
    rm -rf /var/lib/apt/lists/*

WORKDIR /downloads

ENTRYPOINT ["yle-dl"]

