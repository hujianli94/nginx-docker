## 部署 nginx

### 创建 docker network

```
docker network create nginx_proxy -d bridge
```

### 准备 ssl 证书、 xxx_ssl.conf 、 conf.d/xxx.conf

1. ssl 证书文件对应 xxx_ssl.conf 中的 `ssl.d/certs/xxx.crt` 值
2. conf.d/xxx.conf 即 server 入口，见示例
3. 创建 dhparams.pem

```
cd ssl.d/certs
openssl dhparam -out dhparams.pem 2048
```

### 启动 nginx

```
docker-compose up -d
```
