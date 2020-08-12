---
layout:     post
title:      使用docker部署mysql
subtitle:   sql
date:       2017-03-15
author:     TGich
header-img: img/post-bg-cook.jpg
catalog: true
tags:
    - docker
---

生成挂载文件夹：~$ mkdir -p ~/mysql/data ~/mysql/conf ~/mysql/logs
启动mysql容器：~/mysql$ docker run -d -e MYSQL_ROOT_PASSWORD=hIJEQr9qoC5e --name mysql -v /root/mysql/data:/var/lib/mysql -p 3306:3306 mysql --lower_case_table_names=1
进入mysql容器：docker exec -it mysql bash
修改my.cnf：docker cp CONTAINER:FILEPATH LOCALFILEPATH
		    vi LOCALFILEPATH
    docker cp LOCALFILEPATH CONTAINER:FILEPATH
