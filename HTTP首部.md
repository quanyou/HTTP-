#### HTTP首部字段 
##### 4种HTTP首部字段类型
* 通用首部字段（General Header Fields）
* 请求首部字段（Request Header Fields）：补充了请求的附加内容、客户端信息、相应内容相关优先级等信息。
* 响应首部字段（Response Header Fields）：补充了响应的附加内容，也会要求客户端附加额外的内容信息。
* 实体首部字段（Entity Header Fields）：补充了资源内容更新时间等与实体有关的信息。

##### End-to-end首部和Hop-by-hop首部
* 端到端首部（End-to-end Header）:此类别中的首部会转发给请求/响应对应的最终接收目标，且必须保存在由缓存生成的响应中，必须被转发。
* 逐跳首部（Hop-by-hop Header）:此类别中的首部只对单次转发有效，会因通过缓存或代理而不再转发。

#### HTTP/1.1通用首部字段
* 是指请求报文和响应报文双发都会使用的首部。

##### Cache-Control
* 通过指定首部字段Cache-Control的指令，就能操作缓存的工作机制。
* 指令的参数是可选的，多个指令之间通过“,”分隔。首部字段Cache-Control的指令可用于请求及响应时。如：Cache-Control: private, max-age=0, no-cache
* 表示是否能缓存的指令： public 指令  Cache-Control: public   当指定使用public指令时，则明确表明其他用户也可利用缓存。

#### SSL 和 TLS
* HTTPS使用SSL（Secure Sockets Layer）和 TLS（Transport Layer Security）两个协议。
* SSL的慢分两种：一种是通信慢。另一种是指由于大量消耗CPU及内存等资源，导致的处理速度变慢。
* 和使用HTTP相比，网络负载肯能会变慢2到100倍。除去和TCP连接、发送HTTP请求、响应以外，还必须进行SSL通信，因此整体上处理通信量不可避免会增加。
* 另一点SSL必须进行加密处理。在服务器和客户端都需要进行加密和解密的运算处理。会更多的消耗服务器和客户端的硬件资源，导致负载增加。