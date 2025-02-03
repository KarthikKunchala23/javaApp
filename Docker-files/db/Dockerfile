FROM mysql:8.0.33
LABEL Service="DB"
LABEL Project="javaApp"
LABEL Author="Karthik Kunchala"

ENV MYSQL_ROOT_PASSWORD=$MYSQL_ROOT_PASSWORD
ENV MYSQL_DATABASE="accounts"

ADD db_backup.sql /docker-entrypoint-initdb.d/db_backup.sql
EXPOSE 3306
