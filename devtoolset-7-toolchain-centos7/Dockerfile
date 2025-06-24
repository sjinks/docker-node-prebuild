FROM centos/devtoolset-7-toolchain-centos7@sha256:24d4c230cb1fe8e68cefe068458f52f69a1915dd6f6c3ad18aa37c2b8fa3e4e1
USER root
RUN \
    curl -LfSs https://rpm.nodesource.com/setup_20.x | bash - && \
    yum install -y nodejs python3 && \
    yum clean all -y

WORKDIR /usr/src/app
VOLUME /usr/src/app
