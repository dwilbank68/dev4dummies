---
title:  "Ruby - An Alternative to .include?"
date:   2013-12-28 12:26:20 -0800
categories: ruby regex
permalink: regex-shortcut
image: 
---

if you would like to make your code look more obscure and less like Ruby you can do this 

{% highlight ruby %}
dos = "Hegllo"

p /el/ === dos    # => false
p /egl/ === dos   # => true

# is the same as

p dos.include?('el')  # => false
p dos.include?('egl') # => true

{% endhighlight %}