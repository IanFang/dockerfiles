FROM debian:jessie

RUN apt-get update && apt-get install -y --no-install-recommends \
    wget \
    git \
    g++ \
    make \
    sqlite3 \
    python-dev \
    pandoc \
    cython \
    ca-certificates

RUN wget https://bootstrap.pypa.io/get-pip.py && python get-pip.py

RUN pip install -q \
    numpy \
    scipy \
    sklearn \
    py \
    pytest \
    luigi \
    ipython \
    jupyter \
    nbconvert \
    seaborn \
    keras \
    spectral \
    theano \
    tensorflow \
    xgboost \
&& rm -rf /root/.cache/*

RUN apt-get install -y --no-install-recommends \
    openbabel \
    python-openbabel \
    python-rdkit \
    rdkit-data \
    python-pydot \
    python-pygraphviz \
    python-skimage \
    python-pytest \
    python-tk \
&& rm -rf /var/lib/apt/lists/*

RUN mkdir -p $(jupyter --data-dir)/nbextensions && \
    cd $(jupyter --data-dir)/nbextensions && \
    git clone https://github.com/lambdalisue/jupyter-vim-binding vim_binding && \
    jupyter nbextension enable vim_binding/vim_binding

ADD jupyter_notebook_config.py /root/.jupyter/jupyter_notebook_config.py

EXPOSE 8888

CMD '/bin/bash'
