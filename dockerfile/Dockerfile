FROM ubuntu:19.04

RUN apt-get update && apt-get -y dist-upgrade && \
    apt-get install -y gdb wget socat git zsh vim

RUN echo "y" | sh -c "$(wget -O- https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
RUN zsh
RUN git clone https://github.com/longld/peda.git ~/peda
RUN cd ~/ && git clone https://github.com/scwuaptx/Pwngdb.git && \
    cp ~/Pwngdb/.gdbinit ~/

COPY ./helper/* /usr/local/bin/
RUN chmod +x /usr/local/bin/*

EXPOSE 23333
