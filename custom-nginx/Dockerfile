# Simple custom nginx image
# Specify base image
FROM ubuntu:bionic
# Specify the version of nginx you want to install
ENV NGINX_VERSION 1.14.0-0ubuntu1.6
# Perform an apt-get update and then install curl
RUN apt-get update && apt-get install -y curl
# Perform an apt-get update and then install nginx using the version specified above in the ENV
RUN apt-get update && apt-get install -y nginx=$NGINX_VERSION
# Set the working directory
WORKDIR /var/www/html
# Copy our customer index.html file
COPY index.html ./
# Expose the ports
EXPOSE 80
# Specify the command to run on container startup
CMD ["nginx", "-g", "daemon off;"]
# Specify which type of termination signal will be sent to container upon receipt of a stop signal
STOPSIGNAL SIGTERM
# Specify the healthcheck command
HEALTHCHECK CMD curl localhost:80
