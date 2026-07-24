
# 使用客户端进行通话

首先我们明确下面概念

- RustPBX 是服务端，是通信网络的“核心交换机”。相当于电信、联通等等运营商的交换机
- MicroSIP 和 Linphone、等其他 SIP 客户端 都属于客户端，是连接到这个核心的“电话机”。相当于我们的手机

## 使用Linphone通话

- 可以进行音视频通话
- 多平台支持：linux, macos, windows、android、ios

下载地址：[https://www.linphone.org/en/download/](https://www.linphone.org/en/download/)

> **注意!!!**
> 
> 在添加sip账号时，domain只能填 RustPBX 配置里面 `addr` 的值。不能带端口，linphone 默认不支持端口。我最开始被这个坑了很久，如果带了端口，抓包发现时一个数组送到sip服务器的。后面我是突然灵感，把端口去掉，当然 RustPBX 配置里面的端口也更改到默认的，然后一下就注册成功了

## 使用microSIP通话

- 只支持windows
- 只能进行音频通话


microSIP 是支持自定义的端口的



