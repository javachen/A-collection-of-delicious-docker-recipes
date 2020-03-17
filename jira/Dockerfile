# https://gitee.com/pengzhile/atlassian-agent

FROM  atlassian/jira-software:8.7.0

COPY "atlassian-agent.jar" /opt/atlassian/jira/

# 设置启动加载代理包
RUN echo 'export CATALINA_OPTS="-Duser.timezone=GMT+08 -javaagent:/opt/atlassian/jira/atlassian-agent.jar ${CATALINA_OPTS}"' >> /opt/atlassian/jira/bin/setenv.sh