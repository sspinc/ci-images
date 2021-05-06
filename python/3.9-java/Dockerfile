FROM circleci/python:3.9

RUN cd /tmp \
    && wget -q https://github.com/AdoptOpenJDK/openjdk8-binaries/releases/download/jdk8u212-b04/OpenJDK8U-jre_x64_linux_hotspot_8u212b04.tar.gz \
    && tar -xzf OpenJDK8U-jre_x64_linux_hotspot_8u212b04.tar.gz \
    && sudo mv jdk8u212-b04-jre /opt/ \
    && sudo chown -R root:root /opt/jdk8u212-b04-jre \
    && rm OpenJDK8U-jre_x64_linux_hotspot_8u212b04.tar.gz

ENV PATH="/opt/jdk8u212-b04-jre/bin:${PATH}"
ENV JAVA_HOME=/opt/jdk8u212-b04-jre
