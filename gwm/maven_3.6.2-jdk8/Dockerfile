FROM maven:3.6.2-jdk-8
RUN echo "Asia/Shanghai" > /etc/timezone && \
    dpkg-reconfigure -f noninteractive tzdata
COPY ./.ssh /root/
COPY ./setting.xml /usr/share/maven/conf
