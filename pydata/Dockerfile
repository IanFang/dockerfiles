FROM ubuntu:trusty

RUN apt-get update && apt-get install -y \
    gfortran \
    git \
    libblas-dev \
    libboost-dev \
    libboost-python-dev \
    libboost-regex-dev \
    libboost-serialization-dev \
    libboost-system-dev \
    libboost-thread-dev \
    libffi-dev \
    libfreetype6-dev \
    liblapack-dev \
    libopenbabel-dev \
    libpng12-dev \
    libsqlite3-dev \
    libzmq3-dev \
    libyaml-dev \
    openbabel \
    openssl \
    pandoc \
    pkg-config \
    python \
    python-dev \
    python-pip \
    sqlite3 \
&& rm -rf /var/lib/apt/lists/*

RUN pip install numpy && \
    pip install scipy && \
    pip install scikit-learn && \
    pip install pandas && \
    pip install ipython && \
    pip install jupyter && \
    pip install nbconvert && \
    pip install matplotlib && \
    pip install seaborn && \
    pip install keras

RUN pip install --pre xgboost

RUN apt-get update && apt-get install -y \
    python-openbabel \
    librdkit1 \
    python-rdkit \
    rdkit-data \
&& rm -rf /var/lib/apt/lists/*

ENV TF_BINARY_URL=https://storage.googleapis.com/tensorflow/linux/cpu/tensorflow-0.9.0-cp27-none-linux_x86_64.whl

RUN pip install --upgrade \
    $TF_BINARY_URL

RUN rm -rf /root/.cache/*

EXPOSE 8888
