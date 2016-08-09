FROM daocloud.io/ubuntu:trusty
MAINTAINER Wang Yiyang <wangyiyang.kk@gmail.com>
RUN apt-get update && \  
      apt-get install -y python \
                       python-dev \
                       python-pip  \

	&& apt-get clean \
    	&& apt-get autoclean \
    	&& rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN mkdir -p /app
WORKDIR /app
EXPOSE 80
CMD ["bash"]

