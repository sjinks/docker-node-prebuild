FROM centos:7@sha256:be65f488b7764ad3638f236b7b515b3678369a5124c47b8d32916d6487418ea4

RUN \
    curl -LfSs https://rpm.nodesource.com/setup_16.x | bash - && \
    yum install -y nodejs gcc-c++ make python3 && \
    yum clean all -y

WORKDIR /usr/src/app
VOLUME /usr/src/app
