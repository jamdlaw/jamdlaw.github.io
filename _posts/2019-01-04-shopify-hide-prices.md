---
layout: post
title: "Show Product Price on Shopify IF Customer AND Wholesale"
categories: mics
---

A common request from people who have a B2B or Wholesale site is “Can we hide our prices until someone has created an account and we have verified them?”  You can do this in shopify with an App, OR you can wrap all prices in the following IF statement. 

{% highlight liquid %}
    {% raw %}
    	{% if customer and customer.tags contains 'Wholesale'  %}
            {{ current_variant.price | money }}                          
    	{% endif %}
    {% endraw %}
{% endhighlight %}

Please note that we are looking for a customer that is tagged with Wholesale (captial W). 
Liquid code is case sensitive. 



