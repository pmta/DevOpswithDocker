FROM ubuntu

WORKDIR /work
RUN apt-get update && apt-get install -y curl

COPY  curler.sh .
RUN chmod +x curler.sh

CMD ["./curler.sh"]

