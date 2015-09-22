---
layout: post
title: "TCP/IP详解 卷一 第三章：IP协议"
description: "tcp/ip详解 卷一 第三章 IP协议"
category: [networking]
tags: []
---
{% include JB/setup %}
Chapter3 IP: Internet Protocol
===

1. IP协议提供的是不可靠，无连接的数据包传送服务，任何要求的可靠性必须由上层来提供(如TCP)

(1) 不可靠：不能保证IP数据报能成功到达目的地

(2) 无连接：IP协议不维护任何关于数据报的状态信息，每个数据报的处理是相互独立的
