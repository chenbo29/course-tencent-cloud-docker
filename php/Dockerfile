FROM bitnami/php-fpm:7.4
ARG TZ=Asia/Shanghai
RUN ln -snf /usr/share/zoneinfo/${TZ} /etc/localtime \
    && echo ${TZ} > /etc/timezone
# 修正 www-data 在 /var/www 目录下无法读写 .composer 的问题
RUN mkdir -p /var/www && \
  chown www-data:www-data /var/www -R

COPY sourses.list /etc/sources.list
RUN apt-get update && apt-get install supervisor git
