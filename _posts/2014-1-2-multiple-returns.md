---
title:  "How To Get Multiple Return Values From A Method"
date:   2014-1-2 12:26:20 -0800
categories: ruby methods
permalink: multiple-returns
image: 
comments: true
---
I thought this was cool.

Note the square brackets, which make the method return an array.

{% highlight ruby %}
def foo(x)
   [x+5, x*9]
end

a,b = foo(10)

p a #=> 15

p b #=> 90
{% endhighlight %}