FROM maven:3.6.2-jdk-8
RUN echo "Asia/Shanghai" > /etc/timezone && \
    dpkg-reconfigure -f noninteractive tzdata
COPY ./.ssh /root/.ssh
COPY ./settings.xml /usr/share/maven/conf
RUN echo "StrictHostKeyChecking no" >>  /etc/ssh/ssh_config
