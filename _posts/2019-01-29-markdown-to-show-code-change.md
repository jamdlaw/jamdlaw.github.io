---
layout: post
title: "Markdown syntax to show code changes"
categories: markdown
---



The below markup shows how to display code change on Github using markdown.   

{% highlight html %}
    ``` diff
    - delete this code
    + add this code
    ```
{% endhighlight %}

the above code would output

``` diff
- delete this code
+ add this code
```

Make sure the plus and minus lines link up with the back thicks or the red and green highlighting will not work. for example I have the following NOTE the + and - to not line up with the backticks, it is slight but there is a space before the code lines. 

{% highlight html %}
    ``` diff
     - delete this code
     + add this code
    ```
{% endhighlight %}

and the bad output will be displayed below
``` diff
     - delete this code
     + add this code
```