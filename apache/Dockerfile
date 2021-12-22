FROM ubuntu/apache2

WORKDIR /opt/sites/

COPY config_ssh /root/.ssh/config

# apenas atualiza as bibliotecas para instalar outros pacotes
RUN apt-get update  

# install  
RUN apt-get install git vim apache2 php -y
# Extensões do apache
RUN /usr/sbin/a2enmod rewrite ssl proxy proxy_http proxy_balancer ssl && apache2ctl restart

COPY ./apache2.conf.default /etc/apache2/apache2.conf

COPY ./apache2.conf.default /etc/apache2/apache2.conf

# Extensões do PHP
RUN apt-get install -y zlib1g-dev libicu-dev g++ php-soap php-gd php-opcache libapache2-mod-php php-zip php-curl php-xml php-intl php-mbstring php-xml-rpc2 && apache2ctl restart
