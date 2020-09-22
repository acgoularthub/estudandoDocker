FROM ubuntu
MAINTAINER acgoulart
RUN apt update
RUN apt install -y vim wget dialog net-tools
RUN apt install -y nginx
EXPOSE 80
CMD ["nginx"]
