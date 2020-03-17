FROM  atlassian/confluence-server:7.3.3

# 将代理破解包加入容器
COPY "atlassian-agent.jar" /opt/atlassian/confluence/

# 安装微软字体并设置启动加载代理包
RUN apt-get update \
	&& apt-get install ttf-mscorefonts-installer \
	&& echo 'export CATALINA_OPTS="-Dconfluence.document.conversion.fontpath=/usr/share/fonts/truetype/msttcorefonts ${CATALINA_OPTS}"' >> /opt/atlassian/confluence/bin/setenv.sh \
	&& echo 'export CATALINA_OPTS="-javaagent:/opt/atlassian/confluence/atlassian-agent.jar ${CATALINA_OPTS}"' >> /opt/atlassian/confluence/bin/setenv.sh 