**HTTP: HyperText Transfer Portocol, 超文本传输协议**  
**HTML: HyperText Markup Language, 超文本标记语言**  
**URL : Uniform Resource Locator, 统一资源定位符**  
**SGML: Standard Generalized Markup Language, 标准通用标记语言**  

通过发送请求获取服务器资源的Web浏览器等，都可称为客户端（client）。  

### **网络基础TCP/IP**

现在使用的网络是在**TCP/IP**协议族的基础上运行的。HTTP属于其内部的一个**子集**。  

#### TCP/IP 协议族
把互联网相关的协议集合起来总称为TCP/IP.

#### TCP/IP分层管理
TCP/IP协议族按层级分别分为：应用层、传输层、网络层和数据链路层。
##### 应用层
* 为用户提供了应用服务时通讯的活动。常见的FTP(File Transfer Protocol, 文件传输协议), DNS(Domain Name System, 域名系统). HTTP协议属于该层。

##### 传输层
* 传输层是链路两台计算机，进行数据传输的网络通道。两种不同性质的传输协议。TCP（Transmission Controller Protocol, 传输控制协议） 和 UDP(User Data Protocol, 用户数据报协议)。

##### 网络层(网络互连层)
* 网络层的作用就是在众多的网络数据传输通道中选择一条传输路线，将数据包通过传输路线进行传输。**数据包** 是网络传输的最小数据单位。

##### 链路层(数据链路层，网络接口层)
* 处理连接网络的硬件部分，包括操作系统、硬件的设备驱动、NIC（Network Interface Card，网络适配器，网卡），及光纤等。

##### TCP/IP通信传输流
一般由**client**端发出，通过应用层将HTTP请求发送给传输层，传输层(TCP) 将HTTP发送过来的数据进行切割，然后在每个报文上打上标记号以及端口号，然后发送给网络层，网络层（IP）拿到数据后添加目的地的MAC地址，然后发送给链路层。**Server**在链路层接收到数据后，将处理过后的数据按照**链路层->网络层->传输层->应用层**传输，每经过一层都需要剥离在该层的报文。

#### IP、TCP和DNS
##### IP负责传输
* IP（Internet Protocol）网际协议，位于网络层。  
* 作用：将数据包传输给对方。
* IP地址指明了节点被分配到的地址，MAC地址是指网卡所属的固定地址。
  
###### 使用ARP协议凭借MAC地址进行通信：使用ARP(Address Resolution Protocol)协议，是一种用以解析地址的协议，根据通信方的IP地址就可以反查出对应的MAC地址。  
##### 确保可靠性的TCP协议
* TCP位于传输层，提供可靠地**字节流服务**（Bytes Stream Service，为了方便大数据的传输，将大块的数据分割成以报文段（segment）为单位的数据包进行管理。）。  

##### 三次握手（两个标志，SYN（Synchronize, 同步）和ACK（Acknowledegement, 确认））
* Client端向Server 发送一条带有SYN标志的数据包，Server收到数据包验证SYN后，向Client端发送一条带有SYN/ACK标志的数据包表示已收到数据包，然后Client会回传一个带有ACK标志的数据包到Server，代表“握手”结束。

#### DNS服务
* **DNS（Domain Name System）**服务和THHP协议一样位于应用层的协议。提供域名到IP地址之间的解析服务。

#### URI和URL
* **URI**（Uniform Resource Identifier, 统一资源标识符）是由某个协议方案来表示资源的定位标识符。协议方案是指访问资源所使用的协议的类型名称。
* URL使用字符串标识某一互联网资源，URL标识资源的地点，因此URL是URI的子集。




