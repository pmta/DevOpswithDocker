FROM ubuntu

ENV LC_ALL=C.UTF-8 

ENV FRONT_URL="http://localhost:5000"

WORKDIR /

RUN apt-get update && apt-get install -y curl git
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash 
RUN apt-get install -y nodejs
RUN node -v && npm -v

RUN git clone https://github.com/docker-hy/backend-example-docker

WORKDIR /backend-example-docker/ 
RUN npm install 
RUN npm install -g webpack
# RUN npm install -g webpack-cli
RUN npm install -g serve

CMD ["npm", "start"]
# CMD ["serve", "-s", "-l", "8000", "dist"]

EXPOSE 8000

