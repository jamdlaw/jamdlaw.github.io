---
layout: post
title: "Use the reduce() function to sum inventory"
categories: javascript
---

I highly recommend taking a course called [javascript30](https://javascript30.com/), by Wes Bos. It is a free class and you will learn a lot of really good javascript stuff in bit size amounts. Below is a code snippet from that class, but modified to show how it can be used to quickly count inventory stored in an array. 

```javascript
const data = ['Red Shirt', 'Red Shirt', 'Blue Shirt', 
			'Blue Shirt', 'Green Shirt', 'Black Shirt', 'Red Shirt',
			'Pink Shirt', 'Green Shirt', 'Black Shirt', 'Red Shirt',
			'Pink Shirt', 'Red Shirt', 'Blue Shirt', 'Orange Shirt'];
const inventorySum = data.reduce(function(obj, item) {
  if (!obj[item]) {
    obj[item] = 0;
  }
  obj[item]++;
  return obj;
}, {});
console.log(inventorySum);
// output: {"Red Shirt":5,"Blue Shirt":3,"Green Shirt":2,"Black Shirt":2,"Pink Shirt":2,"Orange Shirt":1}
```
 

