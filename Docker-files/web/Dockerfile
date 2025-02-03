FROM nginx
LABEL Service="nginx"
LABEL Project="JavaApp"
LABEL Author="Karthik Kunchala"

RUN rm -rf /etc/nginx/conf.d/default.conf
COPY nginvproapp.conf /etc/nginx/conf.d/vproapp.conf
