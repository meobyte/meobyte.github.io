---
layout: post
title: "Splat Operator in Ruby"
excerpt: "Exploding arguments"
tags: [ruby, operators]
comments: true
---

Say we have an array of arrays. We want to send each of the inner arrays as arguments 
to a method. This can easily be done with the splat operator.

{% highlight ruby %}
combos = [[6, 7, 8], [6, 7, 9], [6, 7, 10], [6, 8, 9], [6, 8, 10], 
          [6, 9, 10], [7, 8, 9], [7, 8, 10], [7, 9, 10], [8, 9, 10]]
          
def pythagorean?(a, b, c)
  a**2 + b**2 == c**2
end

combos.reject { |combo| combo unless pythagorean?(*combo) }
{% endhighlight %}
