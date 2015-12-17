---
title:  "Ruby - Symbol to_proc - A shortcut for the map/collect method"
date:   2013-12-28 12:26:20 -0800
categories: ruby methods
permalink: symbol-to_proc
image: 
---
instead of this:

{% highlight ruby %}
  list = %w[a b c d e f snag]
  p list.map {|el| el.capitalize }
  #=> [“A”, “B”, “C”, “D”, “E”, “F”, “Snag”]
{% endhighlight %}

you can save yourself some typing:

{% highlight ruby %}
  list = %w[a b c d e f snag]
  p list.map(&:capitalize)
  # or even
  p list.map &:capitalize # since parentheses are optional in ruby
  #=> [“A”, “B”, “C”, “D”, “E”, “F”, “Snag”]
{% endhighlight %}



###Explanation...

`.map`, `.each`, and similar methods expect a block. A block is usually denoted by curly braces with a method inside.

1. The colon before the method name is just how you refer to methods in ruby. You pass its name around as a symbol.

2. The ampersand, in this case, is the shorthand for converting a proc to a block.*

3. Your method symbol, however is _not yet_ a proc, so it converts itself into a proc using the symbol object's own internal `.to_proc` method.

4. Then ampersand then turns it into a block and `.map` happily inserts all the elements of the collection into the block one by one, just as before.

Here are a few more examples.

{% highlight ruby %}
  projects.any? &:valid?
  projects.each &:save!
{% endhighlight %}

And finally, this technique is mainly useful when chaining together methods.

{% highlight ruby %}
  projects.collect(&:name).collect(&:downcase)
{% endhighlight %}

*if you don't know what blocks, procs and lambdas are, CodeSchool's RubyBits 1 and 2 courses are good places to start.