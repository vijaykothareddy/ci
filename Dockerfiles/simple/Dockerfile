FROM ubuntu:18.04
RUN echo "I'm simple!"
RUN apt-get update && apt-get -qq -y install curl \
    python3 \
    python3-pip
RUN curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py | python -
RUN poetry export -f requirements.txt --without-hashes -o ./Dockerfiles/simple/requirements.txt
RUN poetry export -f requirements.txt --without-hashes --dev | sed '/^ipython==7.18.1/d'|sed '/^traitlets==5.0.4/d'| \
    tee docker/jupyter/requirements.txt > /dev/null
WORKDIR /app
COPY build-and-push-simple-image.yml /app
COPY ./Dockerfiles/simple/stranger /stranger
RUN cat /stranger
