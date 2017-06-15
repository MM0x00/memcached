# memcached 在线实验环境

## 软件简介

Memcached 是一个高性能的分布式内存对象缓存系统，用于动态Web应用以减轻数据库负载。它通过在内存中缓存数据和对象来减少读取数据库的次数，从而提高动态、数据库驱动网站的速度。Memcached基于一个存储键/值对的hashmap。其守护进程（daemon ）是用C写的，但是客户端可以用任何语言来编写，并通过memcached协议与守护进程通信。

所属类别是数据库

License:BSD 3

特点：
- 协议简单
- 基于libevent的事件处理
- 内置内存存储方式
- memcached不互相通信的分布式

## 软件官网

http://memcached.org/

## Dockerfile 使用方法

### 如何使用
```
$ docker run --name my-memcache -d memcached
```
使用上述命令启动您的memcached容器，然后您可以使用标准链接将应用连接到它：
```
$ docker run --link my-memcache:memcache -d my-app-image
```
然后，memcached服务器的信息将通过该链接以及通过DNS所产生的ENV变量memcache的/etc/hosts。

如何设置memcached的内存使用情况
```
$ docker run --name my-memcache -d memcached memcached -m 64
```
这将使memcache服务器设置为使用64兆字节进行存储。

## 资源链接

- http://memcached.org/
- http://www.runoob.com/Memcached/Memcached-tutorial.html
