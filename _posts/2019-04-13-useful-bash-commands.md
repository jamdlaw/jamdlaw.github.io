---
layout: post
title: "Useful Bash Commands"
categories: shopify
---

# Simple list of bash commnads with short explanation


__Goal__: create a file name myfile.txt

```
touch myfile.txt
```
------
<br><br>
__Goal__: read a file name myfile.txt

```
cat myfile.txt
```
------
<br><br>

__Goal__: copy a myfile.txt file from folder1 to folder2 *for this we expect both folder1 and folder2 to be in the same parent folder*
```
cp ./folder1/myfile.txt ./folder2/myfile.txt
```
------
<br><br>

__Goal__: create a parent and child folder *then* create a text file in new folder structure 

```
mkdir -p parent/child/ | touch parent/child/mystuff.txt
``` 

*-p is the imporant part, without is you will get an error that the parent folder does not exist when it trys to create the child folder*

------
<br><br>
 
__Goal__: see a complete list of all the commands that have been run

```
history
```  
<br><br>
__Goal__: find a file _by name_ somewhere and display it's contents 

```
find --name example.html -exec cat {} \;
```
------
<br><br>
