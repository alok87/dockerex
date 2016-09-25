FROM nginx
MAINTAINER Alok Kumar Singh <alok.singh@practo.com>

# Install custom nginx config
COPY nginx.conf /etc/nginx/
RUN mkdir -p /etc/nginx/sites-available
RUN mkdir -p /etc/nginx/sites-enabled

COPY accounts.conf /etc/nginx/sites-available/app1
RUN ln -s /etc/nginx/sites-available/app1 /etc/nginx/sites-enabled/app1

COPY calendar.conf /etc/nginx/sites-available/app2
RUN ln -s /etc/nginx/sites-available/app2 /etc/nginx/sites-enabled/app2
