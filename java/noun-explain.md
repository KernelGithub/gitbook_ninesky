# 名词解释

1. **RPC: \( Remote Procedure Call  Protocol\) ———— 远程过程调用协议**  
   1. 设计为在应用程序间通信的平台中立的方式，无操作系统和语言的差异，支持多语言

2. ```
   关键词：寻址  序列化(Serialize) 编组(marshal
   ```
3. **RMI: \( Remote Method Invocation \) ** RPC的java版本，EJB的基础技术，构建在TCP/IP协议上的一种远程调用方法。
   1. RMI采用stubs和skeletons来进行远程对象的通讯。stub充当远程对象的客户端代理，有着和远程对象相同的远程接口，远程对象的调用实际是通过改对象的客户端代理对象来完成的。
   2. [http://www.jb51.net/article/68971.htm](http://www.jb51.net/article/68971.htm)
   3. 利用对象序列化来实现远程调用
4. **SOAP \( Simple Object Access Protocol \)：**主要工作是使用标准的xml描述了RPC的请求信息（URI/类/方法/参数/返回值），一般是一段xml
5. **WSDL \( Web Services Description Language \):**描述web服务的，描述怎么访问web服务。也是一段xml



