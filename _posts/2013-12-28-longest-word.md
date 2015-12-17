---
title:  "Ruby - Find The Longest Word In A Sentence"
date:   2013-12-28 12:26:20 -0800
categories: ruby inject algorithm
permalink: longest-word
image: 
comments: true

---
Another fine use of `.inject` straight from the ruby-doc manual

{% highlight ruby %}
words = %w{the longest word this sentence is undoubtedly hocem }

theWinner = words.inject do |longestWord, currentWord|
  longestWord.length > currentWord.length ? longestWord : currentWord
end

p theWinner
{% endhighlight %}