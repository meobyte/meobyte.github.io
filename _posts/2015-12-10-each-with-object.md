---
layout: post
title: "each_with_object"
excerpt: "For easier shoveling."
tags: [ruby, enumerators, patterns]
comments: true
---

How many times have I found myself doing this?

{% highlight ruby %}
def squared(array)
  result = []
  array.each do |value|
    result << value**2
  end
  result
end
{% endhighlight %}

There's an easier way:

{% highlight ruby %}
def squared(array)
  array.each_with_object([]) do |value, result|
    result << value**2
  end
end
{% endhighlight %}