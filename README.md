# nginxcourses
Repository for nginx courses

1 - sudo nano /etc/yum.repos.d/nginx.repo

[nginx]
name=nginx repo
baseurl=http://nginx.org/packages/mainline/centos/7/$basearch/
gpgcheck=0
enabled=1

2. sudo yum update
3. sudo yum install nginx
4. sudo service nginx start
5. sudo systemctl enable nginx
6. sudo mkdir /etc/nginx/ssl
7. sudo cp /tmp/ssl/example.key /etc/nginx/ssl/
8. sudo cp /tmp/ssl/example.pem /etc/nginx/ssl/

9. Добавляем содержимое https://github.com/yyashkin/nginxcourses/blob/master/1.https%20default
в /etc/nginx/conf.d/default.conf

Добавляем 192.168.222.121 nginxtestsite.ru
 в hosts

10. В /etc/nginx/nginx.conf добавляем

    gzip  on;
    gzip_disable “msie6”;
    gzip_types text/plain text/css application/json application/x-javascript text/xml

11. Добавляем proxy_cache_path /var/cache/nginx levels=1:2 keys_zone=all:32m max_size=1g; в nginx.conf
12. Добавляем настройки в конфиги из https://github.com/yyashkin/nginxcourses/blob/master/2.server%20cache%20nginxconf

13. Посмотреть логи apache sudo cat /var/log/httpd/access_log
                    nginx sudo tail -f /var/log/nginx/access.log


Формат логов:

log_format  main  '$remote_addr - $remote_user [$time_local] "$request" '
                      '$status $body_bytes_sent "$http_referer" '
                      '"$http_user_agent" "$http_x_forwarded_for" "$request_time"';




