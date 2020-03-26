---
layout: post
title: "Useful Bash Commands"
categories: bash
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

this one I like to use with connections to servers that I might have accessed in the past, but do not remember the ssh connection 
string, and did not create a server alias. so say the IP addres is 10.5.5.53 I could looks through my history to find the ssh connection like this 
```
history | grep  10.5.5.53
```
------
<br><br>
__Goal__: find a file _by name_ somewhere and display it's contents 

```
find --name example.html -exec cat {} \;
```
------
<br><br>
__Goal__: get the last entires in a log file AND automatically refresh the terminal 
when new log entries appear

```
tail -f /var/log/nginx/error_log
```
------
<br><br>

__Goal__: find a string in a file and then show 10 line before and 20 lines after
```
cat someFile.txt | grep -B10 -A20 some_string_to_find
```
<br><br>
------
