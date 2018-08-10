---
layout: post
title: "Docker Commands"
author: "Malek Atwiz"
---

# Docker commands

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
{% raw %} docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' ContainerID {% endraw %}
{% endhighlight %}

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

* Remove specific image:
{% highlight bash %}
docker rmi ImageID
{% endhighlight %}

* Run container in the background with name:
{% highlight bash %}
docker run -d --name bluewhaleweb webimage
{% endhighlight %}

* Run container and link it to another one with an alias:
{% highlight bash %}
docker run -d -p 5000:5000 --link bluewhaleweb:web someotherimage
{% endhighlight %}

* Build an image and tag it:
{% highlight bash %}
docker build -f PathToDockerfile -t tag .
{% endhighlight %}

* Create a custom network:
{% highlight bash %}
docker network create --driver bridge networkname
{% endhighlight %}

* Run a container in a specific network:
{% highlight bash %}
docker run -d --net=networkname --name conainername imagename
{% endhighlight %}