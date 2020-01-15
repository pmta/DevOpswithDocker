FROM ubuntu:16.04

ENV LC_ALL=C.UTF-8 
ENV API_URL=http://localhost:8000

WORKDIR /

RUN apt-get update && apt-get install -y curl git && \
    curl -sL https://deb.nodesource.com/setup_10.x | bash && \
    apt-get install -y nodejs && \
    node -v && npm -v && \
    git clone https://github.com/docker-hy/frontend-example-docker.git && \
    cd /frontend-example-docker/ && \
    npm install &&  npm install -g webpack && \
    npm install -g serve && \
    npm run build && \
    apt-get purge -y --auto-remove curl git && \ 
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*  && \ 
    useradd -m app && chown -R app:app /frontend-example-docker/

USER app

WORKDIR /frontend-example-docker/ 

CMD ["serve", "-s", "-l", "5000", "dist"]

EXPOSE 5000

