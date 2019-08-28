# inlets-docker

## 1.版本

---

inlets 2.3.2

## 2.说明

---

inlets 结合了反向代理和 websocket 隧道，通过出口节点将内部和开发端点暴露给公网。出口节点可以是 VPS 或具有 IPv4 IP 地址的任何其他计算机，同时还能和SSL结合提供更加安全的通信

本容器主要提供客户端功能，配置非常简单，只需要修改三个参数即可

## 3.变量说明

---

|变量名|默认值|说明|
|:---:|:---:|:---:|
|REMOTE_URL|127.0.0.1:8000|远程主机地址及监听端口，可以是公网IP也可以是私网的|
|TOKEN|    |身份认证密钥|
|UPSTREAM|<http://127.0.0.1:80>|需要映射的本地端口或者局域网内的其他主机的端口，后面必须指定端口号|

## 4.使用方法

---

* 托取镜像

docker pull lunksana/inlets-docker:latest

* 直接运行

docker run --name inlets -d lunksana/inlets-docker:latest -e REMOTE_URL=远程地址及端口号,TOKEN=身份认证字符串,UPSTREAM=本地地址及端口号

> 手动替换掉变量中的参数以符合自身的设定

* 测试一下

打开远程服务器IP,看看是否能否访问
