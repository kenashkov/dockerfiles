FROM kenashkov/php:5.3-base-stretch

# Add hash check c4e1cf6972b2a9c7f2777a18497d83bf713cdbecabb65d3ff62ba441aebb0091 php
# Add hash check for apache
# && ./configure --prefix=/web/apache-2.2/ --enable-mods-shared="all" \
# && './configure' '--prefix=/web/php5.3' '--with-apxs2=/web/apache-2.2/bin/apxs' '--enable-bcmath' '--enable-calendar' '--enable-dbase' '--enable-exif' '--enable-ftp' '--enable-libxml' '--enable-mbstring' '--enable-pdo' '--enable-soap' '--enable-sockets' '--enable-zip' '--with-bz2' '--with-curl' '--with-gd' '--with-mcrypt' '--with-mhash' '--with-mime-magic' '--with-mysql=mysqlnd' '--with-openssl' '--with-pdo-sqlite=shared' '--with-pgsql' '--with-sqlite=shared' '--with-tidy' '--with-xsl' '--with-zlib' '--with-zlib-dir' '--with-pdo-mysql=mysqlnd' '--with-pdo-pgsql' '--with-jpeg-dir' '--with-png-dir' '--with-xpm-dir' '--with-ttf' '--with-freetype-dir' '--with-t1lib' '--enable-gd-native-ttf' '--with-mysqli=mysqlnd' '--with-imap-ssl' '--with-kerberos' '--with-gettext' '--enable-sysvsem' '--enable-sysvshm' '--enable-sysvmsg' '--enable-pcntl' '--enable-opcache' '--enable-debug' \

# '--with-t1lib'
RUN cd /root \
    && wget "http://archive.apache.org/dist/httpd/httpd-2.2.34.tar.bz2" \
    && tar -xjvf httpd-2.2.34.tar.bz2 \
    && cd ./httpd-2.2.34 \
    && ./configure --prefix=/web/apache-2.2/ --enable-mods-shared="all" \    
    && make -j6\
    && make install \

    && cd /root \
    && wget "https://www.php.net/distributions/php-5.3.29.tar.bz2" \
    && tar -xjvf php-5.3.29.tar.bz2 \
    && cd ./php-5.3.29 \
    && './configure' '--prefix=/web/php5.3' '--with-apxs2=/web/apache-2.2/bin/apxs' '--enable-bcmath' '--enable-calendar' '--enable-dbase' '--enable-exif' '--enable-ftp' '--enable-libxml' '--enable-mbstring' '--enable-pdo' '--enable-soap' '--enable-sockets' '--enable-zip' '--with-bz2' '--with-curl' '--with-gd' '--with-mcrypt' '--with-mhash' '--with-mime-magic' '--with-mysql=mysqlnd' '--with-openssl=/usr/local/ssl' '--with-pdo-sqlite=shared' '--with-pgsql' '--with-sqlite=shared' '--with-tidy' '--with-xsl' '--with-zlib' '--with-zlib-dir' '--with-pdo-mysql=mysqlnd' '--with-pdo-pgsql' '--with-jpeg-dir' '--with-png-dir' '--with-xpm-dir' '--with-ttf' '--with-freetype-dir' '--enable-gd-native-ttf' '--with-mysqli=mysqlnd' '--with-imap-ssl' '--with-kerberos' '--with-gettext' '--enable-sysvsem' '--enable-sysvshm' '--enable-sysvmsg' '--enable-pcntl' '--enable-opcache' '--enable-debug' '--with-ssl=/usr/local/ssl' \
    && make -j6\
    && make install
