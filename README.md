# Linux：C、C++、Python、Shell、Java

	系统编程
		进程
		线程

	网络编程
		TCP/IP协议
			TCP、UDP协议
				HTTP协议
					Socket：对TCP/IP协议的封装，HTTP应用层协议包装数据，本身并不是协议，而是一个调用接口(API)，通过Socket，我们才能使用TCP/IP。
				WebSocket：基于TCP传输协议，并依赖HTTP协议进行一次握手，握手成功后，数据就直接从TCP通道传输，属于应用层协议。

	Makefile

	Shell编程



	IP层接收由更低层（网络接口层例如以太网设备驱动程序）发来的数据包，并把该数据包发送到更高层---TCP或UDP层；相反，IP层也把从TCP或UDP层接收来的数据包传送到更低层。
		数据包中含有发送它的主机的地址（源地址）和接收它的主机的地址（目的地址）。

	TCP是面向连接的通信协议，通过三次握手建立连接，通讯完成时要拆除连接，由于TCP是面向连接的所以只能用于端到端的通讯。
		是传输层协议，主要解决数据如何在网络中传输。没有应用层，便无法识别数据内容，如果想要使传输的数据有意义，则必须使用到应用层协议HTTP。
	
	UDP是面向无连接的通讯协议，UDP数据包括目的端口号和源端口号信息，由于通讯不需要连接，所以可以实现广播发送。
		是传输层协议，主要解决数据如何在网络中传输。没有应用层，便无法识别数据内容，如果想要使传输的数据有意义，则必须使用到应用层协议HTTP。

	HTTP是一个通信协议，是应用层协议，主要解决如何包装数据，通过网络传输信息。
	HTTP的生命周期通过 Request 来界定，也就是一个 Request 一个 Response ，那么在 HTTP1.0 中，这次HTTP请求就结束了。在HTTP1.1中进行了改进，使得有一个keep-alive，也就是说，在一个HTTP连接中，
    可以发送多个Request，接收多个Response。但是请记住 Request = Response， 在HTTP中永远是这样，也就是说一个request只能有一个response。而且这个response也是被动的，不能主动发起。
	HTTP底层使用的是TCP。网络上的两个程序通过一个双向的通信连接实现数据的交换，这个连接的一端称为一个socket。

	socket本质是编程接口(API)，是对TCP/IP协议的封装，本身并不是协议，而是一个调用接口(API)，通过Socket，我们才能使用TCP/IP。对端口号(socket)连接过程可以分为三个步骤：服务器监听，客户端请求，连接确认。
	Socket的通讯过程
		服务器端：申请一个socket 绑定到一个IP地址和一个端口上 开启侦听，等待接授连接
		客户端： 申请一个socket 连接服务器（指明IP地址和端口号）
		服务器端接到连接请求后，产生一个新的socket(端口大于1024）与客户端建立连接并进行通讯，原监听socket继续监听。

	Websocket是基于HTTP协议的，或者说借用了HTTP的协议来完成一部分握手。基于TCP的应用层协议，只需要一次连接，以后的数据不需要重新建立连接，可以直接发送，它是基于TCP的，属于和HTTP相同的地位。
	Websocke是全双工通讯的协议，基于TCP传输协议，并复用HTTP的握手通道，属于应用层协议。浏览器和服务器只需要完成一次握手，两者之间就直接可以创建持久性的连接，并进行双向数据传输。
	WebSocket的目的就是解决网络传输中的双向通信的问题，HTTP1.1默认使用持久连接，在一个TCP连接上也可以传输多个Request/Response消息对，但是HTTP的基本模型还是一个Request对应一个Response。

	HTTP、WebSocket等应用层协议，都是基于TCP协议来传输数据的。我们可以把这些高级协议理解成对TCP的封装。大家都使用TCP协议，那么连接和断开，都要遵循TCP协议中的三次握手和四次挥手，
    	只是在连接之后发送的内容不同，或者是断开的时间不同。对于 WebSocket 来说，它必须依赖 HTTP 协议进行一次握手 ，握手成功后，数据就直接从 TCP 通道传输，与 HTTP 无关了。


	


