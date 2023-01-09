# arm_openlitespeed
 
 

apt install build-essential autoconf libtool bison re2c pkg-config libssl-dev libbz2-dev libcurl4-openssl-dev libffi-dev libzip-dev libpng-dev libjpeg-dev libwebp-dev libavif-dev libgmp-dev libc-client-dev libkrb5-dev libldap2-dev libonig-dev libreadline-dev libsodium-dev libxml2-dev libsqlite3-dev -y

 
 
wget https://raw.githubusercontent.com/Steady-WJ/arm_openlitespeed/main/arm-openlitespeed.tar.gz


tar -zxvf arm-openlitespeed.tar.gz


cd openlitespeed-1.7.16


./build.sh


./install.sh



 
wget https://github.com/libexpat/libexpat/releases/download/R_2_5_0/expat-2.5.0.tar.gz

tar -zxvf expat-2.5.0.tar.gz

cd expat-2.5.0

./configure --prefix=/usr/local/expat

make -j 4&&make install

cd /usr/local/lsws/phpbuild/


wget https://raw.githubusercontent.com/Steady-WJ/arm_openlitespeed/main/arm-php5.6.35.tar.gz
 
 
tar -zxvf arm-php5.6.35.tar.gz
 
 
cd php-5.6.35


./configure --prefix=/tmp --disable-all --with-litespeed --enable-session --enable-posix --enable-xml --with-libexpat-dir=/usr/local/expat --with-zlib --enable-sockets --enable-bcmath --enable-json

make -j 4&&make install



cd /usr/local/lsws/admin/fcgi-bin/

rm -rf admin_php

cp /tmp/bin/lsphp /usr/local/lsws/admin/fcgi-bin/admin_php

rm -rf /usr/local/lsws/fcgi-bin/lsphp*

cp /tmp/bin/lsphp /usr/local/lsws/fcgi-bin/lsphp

cp /tmp/bin/lsphp /usr/local/lsws/fcgi-bin/lsphp5

cd /usr/local/lsws/admin/misc

bash admpass.sh

systemctl restart lsws
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
