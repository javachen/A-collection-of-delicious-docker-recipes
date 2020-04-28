FROM  atlassian/jira-software:8.7.0

# https://gitee.com/pengzhile/atlassian-agent
COPY "atlassian-agent.jar" /opt/atlassian/jira/

RUN apt-get update && apt-get install tzdata \
  && ln -snf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && echo Asia/Shanghai >/etc/timezone \
  && dpkg-reconfigure --frontend noninteractive tzdata \
  && echo 'export CATALINA_OPTS="-javaagent:/opt/atlassian/jira/atlassian-agent.jar ${CATALINA_OPTS}"' >> /opt/atlassian/jira/bin/setenv.sh 
