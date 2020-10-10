# 1. How dose a HTTP protocol works?

A request has been sent, the TCP connection created between the client and server, once the response is received, this connection gets closed. Every time you hit a website, new connection is created every single time.

HTTP are **unidirectional**, sender has to trigger a request, and get a response

http://www.google.com

https://www.google.com

# 2. What are WebSockets?

WebSockets are bi-directional, the sender can send data, the receiver also can send data.

WebSockets doesn't close the connection for the first time is open until the client or the server decides to terminate the connection

[ws://www.google.com](ws://www.google.com)

[wss://www.google.com](wss://www.google.com)

# 3. Where/When can WebSockets be used?

- Real time Applications
- Gaming Applications
- Chat Applications

# 4. Realtime WebSockets implementation

www.gdax.com

www.socket.io

# 5. When not to use WebSockets

- Real time updates are not required
- RESTful services are sufficient to get data from server