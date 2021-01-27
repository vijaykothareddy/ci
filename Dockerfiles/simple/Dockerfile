FROM busybox

RUN echo "I'm simple!"
RUN pwd $$ ls -ltr
COPY /vijay-ci/Dockerfiles/simple/stranger /stranger
RUN cat /stranger
