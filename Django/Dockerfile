FROM codercom/code-server:latest

RUN sudo apt update && \
    sudo apt -y install build-essential zlib1g-dev libncurses5-dev libgdbm-dev libnss3-dev libssl-dev libsqlite3-dev libreadline-dev libffi-dev curl libbz2-dev && \
    curl -O https://www.python.org/ftp/python/3.8.2/Python-3.8.2.tar.xz && \
    tar -xf Python-3.8.2.tar.xz && \
    cd Python-3.8.2 && \
    ./configure --enable-optimizations && \
    make -j 4 && \
    sudo make altinstall && \
    python3.8 --version && \
    cd .. && sudo rm -rf Python-3.8.2 Python-3.8.2.tar.xz
RUN sudo apt -y install python3-pip && \
    sudo pip3 install Django && \
    cd /home/coder && \
    django-admin startproject AwesomeThings && \
    cd AwesomeThings && \
    python3 manage.py migrate     

EXPOSE 9000 8000

ENTRYPOINT ["dumb-init", "fixuid", "-q", "/usr/bin/code-server", "--bind-addr", "0.0.0.0:9000", "."]
# ENTRYPOINT ["bash"]

