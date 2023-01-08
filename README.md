# arm_openlitespeed
 
 

apt install build-essential autoconf libtool bison re2c pkg-config libssl-dev libbz2-dev libcurl4-openssl-dev libffi-dev libzip-dev libpng-dev libjpeg-dev libwebp-dev libavif-dev libgmp-dev libc-client-dev libkrb5-dev libldap2-dev libonig-dev libreadline-dev libsodium-dev libxml2-dev libsqlite3-dev

 
 
wget https://raw.githubusercontent.com/Steady-WJ/arm_openlitespeed/main/arm-openlitespeed.tar.gz


tar -zxvf arm-openlitespeed.tar.gz


cd arm-openlitespeed



wget https://raw.githubusercontent.com/Steady-WJ/arm_openlitespeed/main/arm-php5.6.35.tar.gz
 
 
tar -zxvf arm-php5.6.35.tar.gz
 
 
cd arm-php5.6.35
 
 
 
cp /usr/lib/aarch64-linux-gnu/libexpat* /lib/



./configure --with-config-file-path=../conf --disable-all --with-litespeed --enable-session --enable-posix --enable-xml --with-libexpat-dir=/lib/ --with-zlib --enable-sockets --enable-bcmath --enable-json


make && make install



cd /usr/local/lsws/admin/fcgi-bin/

rm -rf admin_php

cp /usr/local/bin/lsphp /usr/local/lsws/admin/fcgi-bin/admin_php

rm -rf /usr/local/lsws/fcgi-bin/lsphp*

cp /usr/local/bin/lsphp /usr/local/lsws/fcgi-bin/lsphp

cp /usr/local/bin/lsphp /usr/local/lsws/fcgi-bin/lsphp5

cd /usr/local/lsws/admin/misc

bash admpass.sh

systemctl restart lsws
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
