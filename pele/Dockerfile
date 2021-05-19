# Copyright Zapata Computing, Inc. All rights reserved.

# Dockerfile for the base QE docker image
FROM zapatacomputing/z-qml:nightly
WORKDIR /app
USER root

#pip install -r pele/requirements.txt fails on install hungarian
# install needed dependencies manually instead
RUN apt-get install gcc gfortran g++ && \
    pip install cython sqlalchemy networkx && \
    git clone https://github.com/pele-python/pele.git && \
    cd pele && \ 
    python3 setup.py build_ext -i --fcompiler=gfortran

ENV PYTHONPATH "${PYTHONPATH}:/app/pele"

WORKDIR /app
ENTRYPOINT bash
