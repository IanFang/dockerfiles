FROM debian:jessie

RUN apt-get update && apt-get install -y --no-install-recommends \
    git \
    g++ \
    make \
    sqlite3 \
    python-dev \
    python-scipy \
    python-matplotlib \
    openbabel \
    pandoc \
    python-pip \
    python-openbabel \
    python-rdkit \
    rdkit-data \
    python-pydot \
    python-pygraphviz \
    python-sklearn \
    python-skimage \
    python-pil \
    python-pytest \
    python-tk \
    cython \
&& rm -rf /var/lib/apt/lists/*

RUN pip install -q ipython jupyter nbconvert seaborn keras spectral theano && \
    pip install -q --pre xgboost && \
    pip install -q --upgrade \
        https://storage.googleapis.com/tensorflow/linux/cpu/tensorflow-0.11.0rc0-cp27-none-linux_x86_64.whl && \
rm -rf /root/.cache/*

EXPOSE 8888
