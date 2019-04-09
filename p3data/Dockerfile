FROM ubuntu:latest

RUN apt-get update && apt-get install -y --no-install-recommends \
    wget \
    git \
    g++ \
    make \
    sqlite3 \
    python3-dev \
    pandoc \
    cython3 \
    libssl-dev \
    swig \
    ca-certificates \
&& rm -rf /var/lib/apt/lists/*

RUN wget https://bootstrap.pypa.io/get-pip.py && \
    python3 get-pip.py && \
    rm get-pip.py

RUN pip3 install \
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
    bokeh \
    mock \
    nltk \
    pybrain \
    tables \
    statsmodels \
    networkx \
    scrapy \
    urllib3 \
    requests \
    beautifulsoup4 \
    pytest \
    configargparse \
    pydot \
    scikit-image \
    configargparse \
    gensim \
    statsmodels \
    pyyaml \
    tpot \
    mlxtend \
    spacy \
    peakutils \
    featuretools \
&& rm -rf /root/.cache/*

RUN pip3 install \
    auto-sklearn \
&& rm -rf /root/.cache/*

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y --no-install-recommends \
    # following packages are installed to python 2 only, use conda to manage?
    # openbabel \
    # python-openbabel \
    # python-rdkit \
    # rdkit-data \
    python3-tk \
    python3-pygraphviz \
&& rm -rf /var/lib/apt/lists/*

RUN mkdir -p $(jupyter --data-dir)/nbextensions && \
    cd $(jupyter --data-dir)/nbextensions && \
    git clone https://github.com/lambdalisue/jupyter-vim-binding vim_binding && \
    jupyter nbextension enable vim_binding/vim_binding

ADD jupyter_notebook_config.py /root/.jupyter/jupyter_notebook_config.py

EXPOSE 8888

WORKDIR /tmp/working

CMD '/bin/bash'

# to run ipython: docker run -v $PWD:/tmp/working -it --rm p3data ipython
# to run jupyter: docker run -v $PWD:/tmp/working -p 8888:8888 -d p3data bash -c "jupyter-notebook --no-browser --ip=\"0.0.0.0\" --notebook-dir=/tmp/working --allow-root"
