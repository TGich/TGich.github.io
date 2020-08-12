---
layout:     post
title:      使用docker部署kibana
subtitle:   sql
date:       2017-06-08
author:     TGich
header-img: img/post-bg-cook.jpg
catalog: true
tags:
    - docker
---

• docker 启动 kibana
$ docker run --name kibana -d -p 5601:5601

• 服务器 kibana 配置文件 kibana.yml
server.host: "0.0.0.0"

• 坑
	1. kibana.yml
	server.host: "0.0.0.0"
	2. vi /etc/sysconfig/iptables
-A INPUT -m state --state NEW -m tcp -p tcp --dport 5601 -j ACCEPT
