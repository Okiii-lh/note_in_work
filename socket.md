### [Errno 57] Socket is not connected

self.recv_data, self.recv_addr = self.socket.recvfrom(1024)
	OSError: [Errno 57] Socket is not connected

查看socket端口号是否被占用

### [WinError 10038] 在一个非套接字上尝试了一个操作

socket先close再调recv就会报错。

