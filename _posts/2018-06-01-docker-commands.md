---
layout: post
title: "Docker Commands"
author: "Malek Atwiz"
---

# Docker commands

## MS SQL Server

* Run MS SQL Server Linux image: ```docker run -e "ACCEPT_EULA=Y" -e "SA_PASSWORD=MyP@ssword!" -p [host port]]:1433 -d --name=[Container Name] microsoft/mssql-server-linux:2017-latest```

* Run command on SQL Server: ```docker exec -it [Container Name] /opt/mssql-tools/bin/sqlcmd -S localhost -U sa -P MyP@ssword!```

* Run in interactive mode: ``` docker run -it ```

* Remove after completion: ``` docker run --rm ```

* Get container IP Address: ``` docker inspect --format="{{range .NetworkSettings.Networks}}{{.IPAddress}} {{end}}" ContainerID ```

* Another test:
{% highlight bash %}
docker run -it
{% endhighlight %}