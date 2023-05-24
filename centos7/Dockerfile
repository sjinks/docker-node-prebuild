FROM centos:8@sha256:a27fd8080b517143cbbbab9dfb7c8571c40d67d534bbdee55bd6c473f432b177

RUN \
    curl -LfSs https://rpm.nodesource.com/setup_16.x | bash - && \
    yum install -y nodejs gcc-c++ make python3 && \
    yum clean all -y

WORKDIR /usr/src/app
VOLUME /usr/src/app
