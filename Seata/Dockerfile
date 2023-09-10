FROM openjdk:8

WORKDIR /home/seata
ENV SEATA_VERSION 1.4.2\
    SEATA_LOG logs

RUN curl -SL https://qiniu-cdn.xcye.xyz/seata-server-1.4.2.tar.gz -o /home/seata-server.tar.gz \
    && tar -xzvf /home/seata-server.tar.gz -C /home \
    && mv /home/seata/seata-server-${SEATA_VERSION}/* /home/seata\
    && rm -rf /home/seata-server.tar.gz /home/seata/seata-server-${SEATA_VERSION} /home/seata/bin/seata-server.bat \
    && ln -snf /usr/share/zoneinfo/$TIME_ZONE /etc/localtime && echo $TIME_ZONE > /etc/timezone

RUN ["/bin/sh", "-c", "ls /home/seata"]
EXPOSE 8091
RUN ["/home/seata/bin/seata-server.sh"]