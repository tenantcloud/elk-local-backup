ARG ES_VERSION

# https://github.com/elastic/elasticsearch-docker

FROM docker.elastic.co/elasticsearch/elasticsearch:${ES_VERSION}

# Add your elasticsearch plugins setup here
# Example: RUN elasticsearch-plugin install analysis-icu

RUN bin/elasticsearch-plugin install --batch repository-s3
RUN echo "-Des.allow_insecure_settings=true" >> config/jvm.options

ADD ./start /start
RUN chmod +x /start

ADD ./restore /restore
RUN chmod +x /restore

WORKDIR /