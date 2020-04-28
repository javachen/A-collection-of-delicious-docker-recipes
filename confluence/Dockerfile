FROM  atlassian/confluence-server:7.5.0-m62-ubuntu

COPY "atlassian-agent.jar" /opt/atlassian/confluence/

RUN apt-get update && apt-get install tzdata \
  && ln -snf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && echo Asia/Shanghai >/etc/timezone \
  && dpkg-reconfigure --frontend noninteractive tzdata \
  && echo 'export CATALINA_OPTS="-javaagent:/opt/atlassian/confluence/atlassian-agent.jar ${CATALINA_OPTS}"' >> /opt/atlassian/confluence/bin/setenv.sh 