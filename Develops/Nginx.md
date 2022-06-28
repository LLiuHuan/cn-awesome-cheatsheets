<!--
 * @Description: 
 * @Author: LLiuHuan
 * @Date: 2021-04-26 15:14:49
 * @LastEditTime: 2022-06-28 22:13:43
 * @LastEditors: LLiuHuan
-->
 
### Nginx 基础  

> 文档：https://nginx.org/en/docs/


```conf
sudo nginx -t # 检查语法
sudo systemctl status nginx # nginx当前状态
sudo systemctl reload nginx # 重新加载nginx
sudo systemctl restart nginx   # 重启nginx
sudo ln -s /etc/nginx/sites-available/example.com /etc/nginx/sites-enabled/ # 链接网站
```

### 常规设置

```conf
# 端口

server {
  #使用HTTP协议
  listen 80 ;
  
  #使用 HTTPS 协议
  listen 443 ssl ;
  
  #使用 IPv6 监听 80 端口
  listen [::]:80 ;
  
  #使用 **only** IPv6 监听端口 80
  listen [::]:80 ipv6only=on ;
}
```

```conf
# 域名

server {
  # 监听 example.com
  server_name example.com;
  
  # 监听多个域名
  server_name example.com www.example.com;
  
  # 监听所有子域名
  server_name *.example.com;
  
  # 监听所有顶级域名
  server_name example.*;
  
  # 监听未指定的主机名
  server_name "";
}
```

### 服务文件

```conf
#静态资源

server {
    listen 80 ;
    server_name example.com ;

    root /path/to/website ；
    #root /www/data/ 例如

    # 如果里面没有'root'，它会寻找 /www/data/index.html
    location / {
    }

    # 如果里面没有'root'，它会寻找/www/data/images/index.html
    location /images/ {
    }

    # 因为里面有'root'，它会寻找/www/media/videos/index.html
    location /videos/ {
        root /www/media;
    }
}
```

### 重定向

```conf
# 301 永久

server {
    #将 www.example.com 重定向到 example.com
    listen 80;
    server_name www.example.com;
    return 301 http://example.com$request_uri;
}

server {
    #重定向http到https
    listen 80;
    server_name example.com;
    return 301 https://example.com$request_uri;
}

```

```conf
# 302 临时

server {
  listen 80;
  server_name yourdomain.com;
  return 302 http://otherdomain.com;
}
```


### 反向代理  

```conf
# 适用于 Node.js、Streamlit、Jupyter 等

# 基本

server {
  listen 80;
  server_name example.com;
  
  location / {
    proxy_pass http://0.0.0.0:3000;
    #其中 0.0.0.0:3000 是绑定在 0.0.0.0 端口 3000 上的 Node.js 服务器
  }
}

# 基本 + (upstream)

upstream node_js {
  server 0.0.0.0:3000;
  #其中 0.0.0.0:3000 是绑定在 0.0.0.0 端口 3000 上的 Node.js 服务器
}

server {
  listen 80;
  server_name example.com;
  
  location / {
    proxy_pass http://node_js;
  }
}

# 升级的连接（对于支持 WebSockets 的应用程序很有用）

upstream node_js {
  server 0.0.0.0:3000;
}

server {
  listen 80;
  server_name example.com;
  
  location / {
    proxy_pass http://node_js;
    proxy_redirect off;
    proxy_http_version 1.1;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection "upgrade";
    proxy_set_header Host $host;
    }
}
```

### HTTPS

```conf
# 大多数 SSL 选项取决于您的应用程序做什么或需要什么

server {
    listen 443 ssl http2;
    server_name example.com;

    ssl on;

    ssl_certificate /path/to/cert.pem;
    ssl_certificate_key /path/to/privkey.pem;

    ssl_stapling on;
    ssl_stapling_verify on;
    ssl_trusted_certificate /path/to/fullchain.pem;

    ssl_protocols TLSv1 TLSv1.1 TLSv1.2;
    ssl_session_timeout 1d;
    ssl_session_cache shared:SSL:50m;
    add_header Strict-Transport-Security max-age=15768000;
}

# 永久重定向到 HTTPS 安全域

server {
  listen 80;
  server_name yourdomain.com;
  return 301 https://$host$request_uri;
}

# 您可以使用 lets-encrypt 轻松保护您的网站/应用程序。
# 文档： https://certbot.eff.org/lets-encrypt/ubuntuxenial-nginx.html
```

### 负载均衡

```conf
# 对于在多个实例中运行的大型应用程序很有用。以下示例用于反向代理
upstream node_js {
  server 0.0.0.0:3000;
  server 0.0.0.0:4000;
  server 127.155.142.421;
}

server {
  listen 80;
  server_name example.com;
  
  location / {
    proxy_pass http://node_js;
  }
}
```

> 其他，之前暂存
### proxy_cache 
- proxy_cache  
  语法：proxy_cache zone|off

  默认为off，即关闭proxy_cache功能，zone为用于存放缓存的内存区域名称。
  例：proxy_cache my_zone;

  从nginx 0.7.66版本开始，proxy_cache机制开启后会检测被代理端的HTTP响应头中的"Cache-Control"、"Expire"头域。
  如，Cache-Control为no-cache时，是不会缓存数据的。

- proxy_cache_bypass  
  语法：proxy_cache_bypass string;

  该参数设定，什么情况下的请求不读取cache而是直接从后端的服务器上获取资源。
  这里的string通常为nginx的一些变量。

  例：proxy_cahce_bypass $cookie_nocache $arg_nocache$arg_comment;
  意思是，如果$cookie_nocache $arg_nocache$arg_comment这些变量的值只要任何一个不为0或者不为空时，
  则响应数据不从cache中获取，而是直接从后端的服务器上获取。  

- proxy_no_cache
  语法：proxy_no_cache string;

  该参数和proxy_cache_bypass类似，用来设定什么情况下不缓存。

  例：proxy_no_cache $cookie_nocache $arg_nocache $arg_comment;
  表示，如果$cookie_nocache $arg_nocache $arg_comment的值只要有一项不为0或者不为空时，不缓存数据。

- proxy_cache_key
 语法：proxy_cache_key string;

  定义cache key，如： proxy_cache_key $scheme$proxy_host$uri$is_args$args; （该值为默认值，一般不用设置）

- proxy_cache_path
  语法：proxy_cache_path path [levels=levels] keys_zone=name:size  [inactive=time] [max_size=size] 

  path设置缓存数据存放的路径；
  levels设置目录层级，如levels=1:2，表示有两级子目录,第一个目录名取md5值的倒数第一个值，第二个目录名取md5值的第2和3个值。
  keys_zone设置内存zone的名字和大小，如keys_zone=my_zone:10m
  inactive设置缓存多长时间就失效，当硬盘上的缓存数据在该时间段内没有被访问过，就会失效了，该数据就会被删除，默认为10s。
  max_size设置硬盘中最多可以缓存多少数据，当到达该数值时，nginx会删除最少访问的数据。

- 示例：
  ```conf
  proxy_cache_path /data/nginx_cache/ levels=1:2 keys_zone=my_zone:10m inactive=300s max_size=5g;

  proxy_cache my_zone;
  ```
### proxy_pass 
- proxy_pass  
  在nginx中配置proxy_pass时，如果是按照^~匹配路径时,要注意proxy_pass后的url最后的/,当加上了/，相当于是绝对根路径，则nginx不会把location中匹配的路径部分代理走;如果没有/，则会把匹配的路径部分也给代理走。
  ```conf
  location ^~ /static/
  {
  proxy_cache my_cache;
  proxy_set_header Host xxx.com;
  proxy_pass http://xxx.com/;
  }
  ```
  如上面的配置，如果请求的url是http://xxx.com/static/test.html  
  会被代理成http://xxx.com/test.html

  而如果这么配置
  ```conf
  location ^~ /static/
  {
  proxy_cache my_cache;
  proxy_set_header Host xxx.com;
  proxy_pass http://xxx.com;
  }
  ```
  则会被代理到http://xxx.com/static/test.htm

  当然，我们可以用如下的rewrite来实现/的功能
  ```conf
  location ^~ /static/
  {
  proxy_cache my_cache;
  proxy_set_header Host xxx.com;
  rewrite /static/(.+)$ /$1 break;
  proxy_pass http://xxx.com;
  }
  ```

- 示例：
  ```conf
  # 示例转自：https://www.jianshu.com/p/b010c9302cd0
  server {
    listen      80;
    server_name www.test.com;

    # 情形A和情形B进行对比，可以知道proxy_pass后带一个URI,可以是斜杠(/)也可以是其他uri，对后端request_uri变量的影响。

    # 情形A
    # 访问 http://www.test.com/testa/aaaa
    # 后端的request_uri为: /testa/aaaa
    location ^~ /testa/ {
        proxy_pass http://127.0.0.1:8801;
    }
    
    # 情形B
    # 访问 http://www.test.com/testb/bbbb
    # 后端的request_uri为: /bbbb
    location ^~ /testb/ {
        proxy_pass http://127.0.0.1:8801/;
    }

    # 情形C
    # 下面这段location是正确的
    location ~ /testc {
        proxy_pass http://127.0.0.1:8801;
    }

    # 情形D说明，当location为正则表达式时，proxy_pass不能包含URI部分。

    # 情形D
    # 下面这段location是错误的
    #
    # nginx -t 时，会报如下错误: 
    #
    # nginx: [emerg] "proxy_pass" cannot have URI part in location given by regular 
    # expression, or inside named location, or inside "if" statement, or inside 
    # "limit_except" block in /opt/app/nginx/conf/vhost/test.conf:17
    # 
    # 当location为正则表达式时，proxy_pass 不能包含URI部分。本例中包含了"/"
    location ~ /testd {
        proxy_pass http://127.0.0.1:8801/;   # 记住，location为正则表达式时，不能这样写！！！
    }

    # 情形E通过变量($request_uri, 也可以是其他变量)，对后端的request_uri进行改写。

    # 情形E
    # 访问 http://www.test.com/ccc/bbbb
    # 后端的request_uri为: /aaa/ccc/bbbb
    location /ccc/ {
        proxy_pass http://127.0.0.1:8801/aaa$request_uri;
    }

    # 情形F和情形G通过rewrite配合break标志,对url进行改写，并改写后端的request_uri。需要注意，proxy_pass地址的URI部分在情形G中无效，不管如何设置，都会被忽略。

    # 情形F
    # 访问 http://www.test.com/namea/ddd
    # 后端的request_uri为: /yongfu?namea=ddd
    location /namea/ {
        rewrite    /namea/([^/]+) /yongfu?namea=$1 break;
        proxy_pass http://127.0.0.1:8801;
    }

    # 情形G
    # 访问 http://www.test.com/nameb/eee
    # 后端的request_uri为: /yongfu?nameb=eee
    location /nameb/ {
        rewrite    /nameb/([^/]+) /yongfu?nameb=$1 break;
        proxy_pass http://127.0.0.1:8801/;
    }

    access_log /data/logs/www/www.test.com.log;
  }
```

server {
  listen      8801;
  server_name www.test.com;

  root        /data/www/test;
  index       index.php index.html;

  rewrite ^(.*)$ /test.php?u=$1 last;

  location ~ \.php$ {
    try_files $uri =404;
    fastcgi_pass unix:/tmp/php-cgi.sock;
    fastcgi_index index.php;
    include fastcgi.conf;
  }

  access_log /data/logs/www/www.test.com.8801.log;
}