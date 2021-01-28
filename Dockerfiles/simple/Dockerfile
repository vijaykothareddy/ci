FROM busybox

RUN echo "I'm simple!"
WORKDIR /app

COPY build-and-push-simple-image.yml /app

COPY ./Dockerfiles/simple/stranger /stranger
RUN cat /stranger
