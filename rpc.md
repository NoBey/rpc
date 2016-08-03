##RPC（Remote Procedure Call Protocol）
----
——远程过程调用协议，它是一种通过网络从远程计算机程序上请求服务，而不需要了解底层网络技术的协议。RPC协议假定某些传输协议的存在，如TCP或UDP，为通信程序之间携带信息数据。在OSI网络通信模型中，RPC跨越了传输层和应用层。RPC使得开发包括网络分布式多程序在内的应用程序更加容易。(可以理解为在tcp／udp上的http这类基于tcp／udp的协议去用自己的方法来实现的一套)，说得通俗一点就是：调用远程计算机上的服务，就像调用本地服务一样。


-- 消息头 --
magic      : 协议魔数，为解码设计
header size: 协议头长度，为扩展设计
version    : 协议版本，为兼容设计
st         : 消息体序列化类型
hb         : 心跳消息标记，为长连接传输层心跳设计
ow         : 单向消息标记，
rp         : 响应消息标记，不置位默认是请求消息
status code: 响应消息状态码
reserved   : 为字节对齐保留
message id : 消息 id
body size  : 消息体长度

-- 消息体 --
采用序列化编码，常见有以下格式
xml   : 如 webservie soap
json  : 如 JSON-RPC
binary: 如 thrift; hession; kryo 等
