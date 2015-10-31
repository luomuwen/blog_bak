title: "session是什么"
date: 2015-09-30 22:50:45
tags:
---

> In computer science, in particular networking, a session is a semi-permanent interactive information interchange, also known as a dialogue, a conversation or a meeting, between two or more communicating devices, or between a computer and user .

以上是来自[wiki][session-wiki]的一段解释。

简单的说，session就是一种半持久性的网络协议，在用户端和服务器端，或者两个或两个以上的设备之间，进行数据交换的一种机制。

我们常常所说的session，指的是HTTP Session。

本文也主要着重对HTTP session进行说明。

HTTP session 在 [wiki][http-session]的说明。

> An HTTP session is a sequence of network request-response transactions.

### 为什么要Session

HTTP协议本身的无状态性。什么叫做无状态，这是一个很关键的概念，在这里简单的说，服务器在处理请求的时候，并不知道这个请求是谁发来的（实际上可以通过IP地址知道，但是这有缺陷）。

这种机制，对于以提供内容为核心的Web1.0，例如门户网站，非常适合。然而对于以应用服务为核心的Web 2.0而言，服务器端必须有能力从请求中提取出请求者的身份信息，以在请求者不用反复输入身份的情况下，提供连续的服务。

### Session的实现























[session-wiki]: https://en.wikipedia.org/wiki/Session_(computer_science)
[http-session]: https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol#HTTP_session

