# Socket

### 1. What's the definition of Socket[^1] :

A **network socket** is a software structure within a **network node**[^2] of a computer network that serves as an endpoint for sending and receiving data across the network. The structure and properties of a socket are defined by an **application programming interface (API)** for the networking architecture. Sockets are created only during the lifetime of a **process of an application**[^3] running in the node.

Because of the standardization of the **TCP/IP** protocols in the development of the Internet, the term network socket is most commonly used in the context of the **Internet Protocol Suite**, and is therefore often also referred to as **Internet socket**[^4]. In this context, a socket is externally identified to other hosts by its **socket address**[^5], which is the triad of transport protocol, IP address, and port number.

The term *socket* is also used for the software endpoint of node-internal **inter-process communication(IPC)**[^6], which often uses the same API as a network socket.







# Representational State Transfer (Rest)

**REST**[^7] is a software architectural style that defines a set of constraints to be used for creating Web services. Web services that conform to the REST architectural style, called **RESTful Web** services, provide interoperability between computer systems on the internet. RESTful Web services allow the requesting systems to access and manipulate textual representations of Web resources by using a uniform and predefined set of **stateless**[^8] operations. Other kinds of Web services, such as SOAP Web services, expose their own arbitrary sets of operations.

:clapper: [推荐视频](https://www.youtube.com/watch?v=7YcW25PHnAA)



# Serverless

### 1. What is Serverless

- No servers to provision or manage
- Automatically scales with usage
- Never pay for idle
- Highly available

### 2. Serverless services

- Amazon DynamoDB
- Amazon API Gateway
- AWS Step Functions
- Amazon Simple Queue Service
- AWS Lambda

A compute service that lets you run code without provisioning or managing servers

### 3. What is Container

Standard unit of software that packages up code and all its dependencies

The application runs quickly and reliably from one computing environment to another

### 4. Container Orchestrators

- Kubemetes (K8)
- Amazon EKS
- Amazon ECS
- Docker Swarm



|                          Serverless                          |                          Container                           |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
| Underlying infrastructure managed by Could Provider<br />Scales automatically<br />No Patching headache | User control underlying infrastructure-VM Size, OS, AMI etc.<br />Requires management and orchestration<br />Need to make master node HA, Handle VM failover, AMI rehydration etc. |
| Can't install software (e.g. Webserver, Appserver) in underlying environment<br />Code libraries can be installed | Install almost every software<br />Prepackaged images with different softwares available |
| Easy selection of compute power<br />128 MB to 3 GB memory<br />1 sec to 15 Minutes time limit | Adjustment of VM parameters requires some work<br />Think of it as changing EC2 instance type on a running instance |
|    No attached hard disk, deployment package size limited    |                 Hard Disks attached to nodes                 |
| **Easier to onboard, focus on solving business problem from get go** |     **Complete control of environment, rich ecosystem**      |





[^1]: 套接字
[^2]: 网络节点
[^3]: 应用程序进程
[^4]: 网络套接字
[^5]:  套接字地址
[^6]: 节点内部进程间通信
[^7]: 表现层状态转换
[^8]: 无状态协议

