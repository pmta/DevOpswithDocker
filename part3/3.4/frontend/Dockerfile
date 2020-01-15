FROM node:alpine

ENV API_URL=http://localhost:8000

WORKDIR /

RUN apk add --no-cache git && \
    git clone https://github.com/docker-hy/frontend-example-docker.git && \
    cd /frontend-example-docker/ && \
    npm install && npm run build && \
    npm install -g serve && \
    adduser -D app && chown -R app:app /frontend-example-docker/ && \
    apk del git apk-tools scanelf

USER app

WORKDIR /frontend-example-docker/ 

CMD ["serve", "-s", "-l", "5000", "dist"]

EXPOSE 5000

