###mac下rabbitmq 的php扩展

##### 一、rabbitmq-c  扩展安装
git clone git://github.com/alanxz/rabbitmq-c.git
cd rabbitmq-c
mkdir build && cd build 
cmake -DCMAKE_INSTALL_PREFIX=/usr/local -DOPENSSL_ROOT_DIR=/usr/local/opt/openssl -DOPENSSL_INCLUDE_DIR=/usr/local/opt/openssl/include  ..
cmake --build . --target install

##### 二.ampp  扩展安装
wget http://pear.php.net/go-pear.phar
php -d detect_unicode=0 go-pear.phar
~/pear/bin/pecl install amqp

##### rabbitmq 的服务安装
brew install rabbitmq
rabbitmq-server -detached 后台启动服务