FROM codercom/code-server:latest

RUN sudo apt -y install openjdk-8-jdk  

EXPOSE 9000 8000

ENTRYPOINT ["dumb-init", "fixuid", "-q", "/usr/bin/code-server", "--bind-addr", "0.0.0.0:9000", "."]
# ENTRYPOINT ["bash"]
