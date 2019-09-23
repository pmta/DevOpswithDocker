FROM ubuntu

ENV LC_ALL=C.UTF-8 
ENV API_URL=http://localhost:8000

WORKDIR /

RUN apt-get update && apt-get install -y curl git
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash 
RUN apt-get install -y nodejs
RUN node -v && npm -v

RUN git clone https://github.com/docker-hy/frontend-example-docker.git

WORKDIR /frontend-example-docker/ 
RUN npm install 
RUN npm install -g webpack
# RUN npm install -g webpack-cli
RUN npm install -g serve

RUN npm run build

CMD ["serve", "-s", "-l", "5000", "dist"]

EXPOSE 5000

