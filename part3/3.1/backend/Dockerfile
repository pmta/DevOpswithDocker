FROM ubuntu:16.04

ENV LC_ALL=C.UTF-8 
ENV FRONT_URL="http://localhost:5000"

WORKDIR /

RUN apt-get update && apt-get install -y curl git && \
    curl -sL https://deb.nodesource.com/setup_10.x | bash  && \
    apt-get install -y nodejs && \
    node -v && npm -v && \
    git clone https://github.com/docker-hy/backend-example-docker && \
    apt-get purge -y --auto-remove curl git && \ 
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* 
    
WORKDIR /backend-example-docker/ 
RUN npm install && npm install -g webpack &&  npm install -g serve


CMD ["npm", "start"]

EXPOSE 8000
