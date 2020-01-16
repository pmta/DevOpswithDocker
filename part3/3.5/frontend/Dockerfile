FROM node:alpine as build-stage

WORKDIR /
RUN apk add --no-cache git && \
    git clone https://github.com/docker-hy/frontend-example-docker.git && \
    cd /frontend-example-docker/ && \
    npm install && npm run build 


FROM node:alpine 

ENV API_URL=http://localhost:8000
WORKDIR / 

RUN npm install -g serve && \
    adduser -D app && mkdir /dist/ && chown -R app:app /dist/

COPY --chown=app:app --from=build-stage /frontend-example-docker/dist/* /dist/

USER app
CMD ["serve", "-s", "-l", "5000", "dist"]

EXPOSE 5000

