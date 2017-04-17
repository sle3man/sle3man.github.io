---
layout: default
title: Psiphon Proxy: Network Analysis
date: 2017-04-16 22:33
---

With proxies and VPNs being cast into the spotlight by the general public, I thought I would analyze the traffic of Psiphon proxy and
see if it's worth looking into as an everyday tool for encrypted network connectivity.

[Excerpt from their website:](https://www.psiphon3.com/en/index.html)

>Psiphon is a circumvention tool from Psiphon Inc. that utilizes VPN, SSH and HTTP Proxy technology to provide you with uncensored access to Internet content. Your Psiphon client will automatically learn about new access points to maximize your chances of bypassing censorship.
>Psiphon is designed to provide you with open access to online content. Psiphon does not increase your online privacy, and should not be considered or used as an online security tool.

As the quote block explains, Psiphon is not meant to be used as a tool to provide anonymity or security. It is a tool meant to circumvent censors and the like.

In this blog post I will perform an analysis of the network traffic flow of the application and provide some insight on how Psiphon proxy works.



