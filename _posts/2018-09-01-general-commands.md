---
layout: post
title: "General Commands"
author: "Malek Atwiz"
---

# General commands

* Create PFX: 
{% highlight bash %}
openssl pkcs12 -export -out auth.skybot.io.pfx -inkey private.key -in certificate.crt -in ca_bundle.crt
{% endhighlight %}

* ngrok port forwarding: 
{% highlight bash %}
ngrok http [port] -host-header="localhost:[port]"
{% endhighlight %}