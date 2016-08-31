FROM debian:jessie
MAINTAINER xingang.fang@gmail.com


RUN apt-get clean && \
    apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -yq octave

RUN apt-get autoclean && apt-get clean
RUN rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN useradd -ms /bin/bash octave
RUN mkdir /home/octave/source
RUN chown -R octave:octave /home/octave/

USER octave
WORKDIR /home/octave

VOLUME ["/home/octave/source"]
ENTRYPOINT ["octave"]