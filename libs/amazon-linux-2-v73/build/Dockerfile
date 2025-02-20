FROM library/centos:6.8

ENV PHP=php73

RUN yum install -y \
        https://dl.fedoraproject.org/pub/epel/epel-release-latest-6.noarch.rpm \
        https://rpms.remirepo.net/enterprise/remi-release-6.rpm \
        yum-utils \
        epel-release \
        curl

RUN yum-config-manager --enable remi
RUN yum update -y && yum upgrade -y
RUN yum -y install patchelf

RUN yum install -y \
        ${PHP}-php-apcu \
        ${PHP}-php-bcmath \
        ${PHP}-php-cli \
        ${PHP}-php-cgi \
        ${PHP}-php-ds \
        ${PHP}-php-fpm \
        ${PHP}-php-gd \
        ${PHP}-php-imap \
        ${PHP}-php-intl \
        ${PHP}-php-json \
        ${PHP}-php-mbstring \
        ${PHP}-php-mysqli \
        ${PHP}-php-mysqlnd \
        ${PHP}-php-opcache \
        ${PHP}-php-pdo \
        ${PHP}-php-phalcon \
        ${PHP}-php-pgsql \
        ${PHP}-php-ssh2 \
        ${PHP}-php-soap \
        ${PHP}-php-sodium \
        ${PHP}-php-swoole \
        ${PHP}-php-tokenizer \
        ${PHP}-php-xml \
        ${PHP}-php-xmlrpc

RUN curl -sS https://getcomposer.org/installer | ${PHP} -- --install-dir=/usr/bin --filename=composer

# $ORIGIN refers to the current directory, don't evaluate it, use the single quotes
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/bin/php
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/bin/php-cgi
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/sbin/php-fpm
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/apcu.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/bcmath.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/bz2.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/calendar.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/ctype.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/curl.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/dom.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/ds.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/exif.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/fileinfo.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/ftp.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/gd.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/gettext.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/iconv.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/imap.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/intl.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/json.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/mbstring.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/mysqli.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/mysqlnd.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/pdo.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/pdo_mysql.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/pdo_pgsql.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/pdo_sqlite.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/pgsql.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/phalcon.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/phar.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/simplexml.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/soap.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/sockets.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/sodium.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/sqlite3.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/ssh2.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/swoole.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/tokenizer.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/xml.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/xmlreader.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/xmlrpc.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/xmlwriter.so
RUN patchelf --set-rpath '$ORIGIN' /opt/remi/${PHP}/root/usr/lib64/php/modules/xsl.so

WORKDIR /var/task

ADD ./conf /var/task/php/
