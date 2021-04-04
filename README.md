# Websites

xlui.app 及其子域名的相关部署文档与源码。

## xlui.app

拷贝 `xlui.app` 目录下的代码到 Nginx 域名目录下即可。

## promo.xlui.app

拷贝 `promo.xlui.app` 目录下的代码到 Nginx 域名目录下即可。

## sh.xlui.app

```bash
git clone https://github.com/xlui/scripts
cd scripts
rm -f /home/wwwroot/sh.xlui.app/*
cp ArchLinux/arch.sh /home/wwwroot/sh.xlui.app/arch
cp BBR/bbr.sh /home/wwwroot/sh.xlui.app/bbr
cp VIM/vim.sh /home/wwwroot/sh.xlui.app/vim
wget -O /home/wwwroot/sh.xlui.app/ss https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-libev-debian.sh
```

## vault.xlui.app

BitwardenRS 私有化部署。

## s.xlui.app

短链接服务。

```bash
docker run  -d --restart always --name short -p 127.0.0.1:9000:5000 -e DOMAIN=https://s.xlui.app/ xlui/short:v1.2
vim /path/to/nignx/conf/s.xlui.app.conf
```

```
location / {
    proxy_pass http://127.0.0.1:9000/;
    proxy_redirect off;
    proxy_set_header    Host                $host;
    proxy_set_header    X-Real-IP           $remote_addr;
    proxy_set_header    X-Forwarded-For     $proxy_add_x_forwarded_for;
    proxy_set_header    X-Forwarded-Proto   $scheme;
}
```