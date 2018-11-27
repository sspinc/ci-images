FROM circleci/openjdk:8

RUN sudo apt-get install python python-pip python-setuptools postgresql-client -y --no-install-recommends \
        && sudo pip install wheel \
        && sudo pip install awscli

ENV _JAVA_OPTIONS=-Djdk.net.URLClassPath.disableClassPathURLCheck=true
