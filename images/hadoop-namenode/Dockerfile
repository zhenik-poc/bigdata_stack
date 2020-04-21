# Note: This Dockerfile is based on https://hub.docker.com/r/bde2020/hadoop-namenode
# The following changes have been made:
#
# 1. Hadoop updated to 2.8.5

FROM johannestang/hadoop-base:2.0.0-hadoop3.2.1-java8

HEALTHCHECK CMD curl -f http://localhost:9870/ || exit 1

ENV HDFS_CONF_dfs_namenode_name_dir=file:///hadoop/dfs/name
RUN mkdir -p /hadoop/dfs/name
VOLUME /hadoop/dfs/name

ADD run.sh /run.sh
RUN chmod a+x /run.sh

EXPOSE 9870

CMD ["/run.sh"]
