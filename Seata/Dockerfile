FROM openjdk:8

WORKDIR /home/seata
ENV SEATA_VERSION 1.4.2\
    SEATA_LOG logs
RUN mkdir -p /home/seata

RUN curl -SL https://qiniu-cdn.xcye.xyz/seata-server-1.4.2.tar.gz -o /home/seata/seata-server.tar.gz \
    && tar -xzvf /home/seata/seata-server.tar.gz -C /home/seata \
    && mv /home/seata/seata/seata-server-1.4.2/* /home/seata\
    && rm -rf /home/seata/seata-server.tar.gz \
    && ln -snf /usr/share/zoneinfo/$TIME_ZONE /etc/localtime && echo $TIME_ZONE > /etc/timezone

RUN ["/bin/sh", "-c", "ls /home/seata"]
EXPOSE 8091
RUN ["/home/seata/bin/seata-server.sh"]