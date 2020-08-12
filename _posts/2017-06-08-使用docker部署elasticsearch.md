---
layout:     post
title:      使用docker部署elasticsearch
subtitle:   sql
date:       2017-06-08
author:     TGich
header-img: img/post-bg-cook.jpg
catalog: true
tags:
    - docker
---

• docker 启动 elasticsearch
$ docker run --name elasticsearch -d -p 9200:9200 -e "httphost=0.0.0.0" -e "transport.host=127.0.0.1" elasticsearch
• 通信
1. Java API
2. HTTP RESTful API json
• 计算集群中文件的数量
···shell
	curl -XGET '10.14.125.230:9200/_count?pretty' -d '
{
    "query": {
        "match_all": {}
    }
}'
```

• 服务器 elasticsearch 配置文件 elasticsearch.yml
network.host: 0.0.0.0

• 坑:
3. http://www.cnblogs.com/sloveling/p/elasticsearch.html
4. vi /etc/sysconfig/iptables
-A INPUT -m state --state NEW -m tcp -p tcp --dport 9200 -jACCEPT
/etc/init.d/iptables stop
