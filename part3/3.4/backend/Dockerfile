FROM node:alpine

# ENV LC_ALL=C.UTF-8 
ENV FRONT_URL="http://localhost:5000"

WORKDIR /

RUN apk add --no-cache git && \
    git clone https://github.com/docker-hy/backend-example-docker && \
    cd /backend-example-docker/ && npm install && \
    adduser -D app && chown -R app:app /backend-example-docker/ && \
    apk del git apk-tools scanelf

USER app
WORKDIR /backend-example-docker/ 

CMD ["npm", "start"]

EXPOSE 8000
