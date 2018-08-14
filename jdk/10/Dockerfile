FROM openjdk:10

ARG MAVEN_VERSION=3.5.3
ARG DOCKER_VERSION=17.12.0-ce
ARG SONAR_SCANNER_VERSION=3.2.0.1227

RUN mkdir /usr/local/maven \
        && curl -sSL https://archive.apache.org/dist/maven/maven-3/${MAVEN_VERSION}/binaries/apache-maven-${MAVEN_VERSION}-bin.tar.gz \
        | tar -xzC /usr/local/maven --strip-components 1 \
        && curl -sSL https://download.docker.com/linux/static/stable/x86_64/docker-${DOCKER_VERSION}.tgz | tar -xzC /usr/local/bin --strip-components 1 \
        && apt-get update \
        && apt-get install make python python-pip python-setuptools -y --no-install-recommends \
        && rm -rf /var/lib/apt/lists/* \
        && pip install wheel \
        && pip install awscli \
        && curl -sSL https://sonarsource.bintray.com/Distribution/sonar-scanner-cli/sonar-scanner-cli-${SONAR_SCANNER_VERSION}-linux.zip -o /tmp/sonar.zip \
        && unzip -d /opt tmp/sonar.zip \
        && rm /tmp/sonar.zip \
        && mkdir /code

ENV MAVEN_HOME /usr/local/maven
ENV PATH "$PATH:/usr/local/maven/bin:/code/bin:/opt/sonar-scanner-${SONAR_SCANNER_VERSION}-linux/bin"
