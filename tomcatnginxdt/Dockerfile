FROM tomcat:9.0.37
#RUN mkdir -p /usr/local/tomcat/conf

ENV TZ 'Europe/Kiev'

RUN echo $TZ > /etc/timezone && \
    apt-get update && apt-get install -y tzdata && \
    rm /etc/localtime && \
    ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && \
    dpkg-reconfigure -f noninteractive tzdata && \
    apt-get clean


COPY tomcat-users.xml /usr/local/tomcat/conf/
COPY context.xml /usr/local/tomcat/conf/
COPY context.xml /usr/local/tomcat/webapps/manager/META-INF/
COPY web.xml /usr/local/tomcat/webapps/manager/WEB-INF/
COPY server.xml /usr/local/tomcat/conf/
COPY ROOT##*.war /usr/local/tomcat/webapps/

CMD ["catalina.sh", "run"] 