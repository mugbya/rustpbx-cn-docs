

## 更改默认配置 

打开 config.toml.example 文件，找到 proxy

首先把 addr 需要改成非0.0.0.0的IP, 否则后续会添加不了用户

其次是吧 udp_port 改成默认的 5060。这个主要是解决linephone不支持非默认端口的问题。也是导致一直添加不了用户

```toml
[proxy]
addr = "192.168.1.100"
udp_port = 5060
...

```
