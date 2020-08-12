---
layout:     post
title:      使用docker部署logstash
subtitle:   sql
date:       2017-06-08
author:     TGich
header-img: img/post-bg-cook.jpg
catalog: true
tags:
    - docker
---


• docker 启动 logstash
$ docker run -it --rm logstash -e 'input { stdin { } } output { stdout { } }'

• docker 使用配置文件启动 logstash
$ docker run -it --rm -v "$PWD":/config-dir logstash -f /config-dir/logstash.conf

• 服务器使用配置文件启动 logstash
$ ./bin/logstash -f /mnt/logstash-5.4.1/config/logstash.conf

• 坑
	1. 启动 logstash 路径不能有空格
	2. 中文乱码
[2017-06-15T10:29:54,182][WARN ][logstash.codecs.line     ] Received an event that has a different character encoding than you configured. {:text=>"\\xCB?\\r", :expected_charset=>"UTF-8"}
