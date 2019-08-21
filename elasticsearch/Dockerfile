FROM bellsoft/liberica-openjdk-debian

RUN apt-get update && \
	apt-get install -y curl wget zip unzip procps && \
	rm -rf /var/lib/apt/lists/* && \
    wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-5.6.8.deb && \
    apt-get install "./elasticsearch-5.6.8.deb" && \
    sed -i "$ a transport.host: localhost\ntransport.tcp.port: 9300\nhttp.port: 9200\nnetwork.bind_host: 0.0.0.0" /etc/elasticsearch/elasticsearch.yml && \
    sed -i "s/-Xms2g/-Xms512m/g" /etc/elasticsearch/jvm.options && \
    sed -i "s/-Xmx2g/-Xmx512m/g" /etc/elasticsearch/jvm.options && \
    rm -rf "./elasticsearch-5.6.8.deb"

COPY docker-entrypoint.sh .

RUN chmod a+x docker-entrypoint.sh

EXPOSE 9200

ENTRYPOINT ["./docker-entrypoint.sh"]
