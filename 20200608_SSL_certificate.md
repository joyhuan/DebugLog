# SSL_connect certificate verify failed
## Bug 
SSL_connect returned=1 errno=0 state=SSLv3 read server certificate B: certificate verify failed

## Cause 
Ruby can't find any root certificates to trust.

## Solution 
[Stack Overflow](https://stackoverflow.com/questions/4528101/ssl-connect-returned-1-errno-0-state-sslv3-read-server-certificate-b-certificat)

Solution 0
```
Download the cacert.pem file from http://curl.haxx.se/ca/cacert.pem. Save this file to C:\RailsInstaller\cacert.pem.

Now make ruby aware of your certificate authority bundle by setting SSL_CERT_FILE. To set this in your current command prompt session, type:

set SSL_CERT_FILE=C:\RailsInstaller\cacert.pem

To make this a permanent setting, add this in your control panel.
```
Solution 1
```
rvm reinstall 2.2.3 --disable-binary
```
## Thought 
If you check the Stack Overflow link, you will find there are two totally different solutions that get high votes. 

Interestingly, I got to use them both at two different times to solve the SSL_connect certificate verification error. The first time I used solution 0 to notify Ruby of the root certificates to trust. It worked until the next week it failed again. For this time I used solution 1 to update Ruby version and the error was solved again. 

## Side 
When I tried to resolve a [make problem](https://github.com/Zhenye-Na/CSAPP-Labs/blob/master/codes/code-all/Makefile~) in [CSAPP](http://csapp.cs.cmu.edu/3e/code.html) caused by linking, I came across a [Docker tutorial](https://zhenye-na.github.io/2019/09/29/docker-practical-guide.html), which leads to [this SSL binge tutorial](https://jasonhzy.github.io/2018/02/01/ssl-cert/). It's simply amazing how interesting technologies are connected. Years ago, I found clueless how it was possible to learn so much about programming. I was too daunted to start my first step. However, once I started to pick up something that interests me(in my case Linux), it was surprisingly fast how all sorts of exciting technologies become relevent. While many people prefer DFS-search diving in the topics that interest them most, I prefer BFS unless I find something that I really need to be strong at in which case I will apply DFS. 
