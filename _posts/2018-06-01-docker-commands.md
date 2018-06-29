---
layout: post
title: "Docker Commands"
author: "Malek Atwiz"
---

# Docker commands

## MS SQL Server

* Run MS SQL Server Linux image: 
{% highlight bash %}
docker run -e "ACCEPT_EULA=Y" -e "SA_PASSWORD=MyP@ssword!" -p [host port]]:1433 -d --name=[Container Name] microsoft/mssql-server-linux:2017-latest
{% endhighlight %}

* Run command on SQL Server: 
{% highlight bash %}
docker exec -it [Container Name] /opt/mssql-tools/bin/sqlcmd -S localhost -U sa -P MyP@ssword!
{% endhighlight %}

* Run in interactive mode: 
{% highlight bash %}
docker run -it
{% endhighlight %}

* Remove after completion:
{% highlight bash %}
docker run --rm
{% endhighlight %}

* Get container IP Address:
{% highlight bash %}
docker inspect --format="{{range .NetworkSettings.Networks}}{{.IPAddress}} {{end}}" ContainerID {% endhighlight %}

* List images:
{% highlight bash %}
docker image ls
{% endhighlight %}

* List containers:
{% highlight bash %}
docker container ls
docker container ls --all
docker container ls -aq
{% endhighlight %}