# mac运行sudo nginx 报错解决方法
在mac10.13.2上用brew安装nginx，sudo nginx 就会报出如下错误
## 问题一：
dyld: Library not loaded: /usr/local/opt/pcre/lib/libpcre.1.dylib
Reference from: /usr/local/bin/nginx
Reason: image not found
[1] 6255 abort sudo nginx

### 解决：
$ brew reinstall pcre && brew unlink pcre && brew link pcre

## 问题二：
dyld: Library not loaded: /usr/local/opt/openssl/lib/libssl.1.0.0.dylib

### 解决：
$ brew remove openssl  

and then

$ brew install openssl

## 问题三：
dyld: Library not loaded: /usr/local/opt/gettext/lib/libintl.8.dylib
### 解决：
$ brew remove gnu-getopt ; brew install --build-from-source gnu-getopt
## 问题四：
dyld: Library not loaded: /usr/local/opt/icu4c/lib/libicui18n.53.dylib

### 解决：
$ brew remove php54
$ brew install php54 --with-your-args
$ brew install php54-intl
