FROM openjdk:17-jdk AS BUILD_IMAGE 
RUN apt-get update && apt-get install maven -y
ENV JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64
ENV PATH=$JAVA_HOME/bin:$PATH
RUN git clone https://github.com/KarthikKunchala23/javaApp.git
WORKDIR /javaApp
RUN java -version
RUN mvn --version
RUN mvn clean install -DskipTests -U
RUN cd javaApp && git checkout Development && mvn clean install

FROM tomcat:9-jre17
LABEL Service="tomcat"
LABEL Project="JavaApp"
LABEL Author="Karthik Kunchala"
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=BUILD_IMAGE /javaApp/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
CMD ["catalina.sh", "run"] 