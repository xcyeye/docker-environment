FROM openjdk:8

WORKDIR /home/seata
ENV SEATA_VERSION 1.7.1\
    SEATA_LOG logs
RUN mkdir -p /home/seata \
#RUN curl -SL https://github.com/seata/seata/releases/download/v${SEATA_VERSION}/seata-server-${SEATA_VERSION}.tar.gz -o /home/seata/seata-server.tar.gz \
#    && tar -xzvf /home/seata/seata-server.tar.gz -C /home/seata \
#    && mv /home/seata/seata/seata-server-${SEATA_VERSION}/* /home/seata\
#    && rm -rf /home/seata/seata-server.tar.gz \
#    && rm /home/seata/conf/registry.conf /home/seata/conf/file.conf\
#    && ln -snf /usr/share/zoneinfo/$TIME_ZONE /etc/localtime && echo $TIME_ZONE > /etc/timezone

RUN curl -SL https://qiniu-cdn.xcye.xyz/seata-server-1.7.1.tar.gz -o /home/seata/seata-server.tar.gz \
    && tar -xzvf /home/seata/seata-server.tar.gz -C /home/seata \
    && mv /home/seata/seata/seata-server-1.7.1/* /home/seata\
    && rm -rf /home/seata/seata-server.tar.gz \
    && rm /home/seata/conf/registry.conf /home/seata/conf/file.conf\
    && ln -snf /usr/share/zoneinfo/$TIME_ZONE /etc/localtime && echo $TIME_ZONE > /etc/timezone

RUN ["/bin/sh", "-c", "ls /home/seata"]
EXPOSE 8091
ENTRYPOINT ["/home/seata/bin/seata-server.sh"]