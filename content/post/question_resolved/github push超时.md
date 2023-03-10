---
title: GitHub push超时 问题解决
description: GitHub push超时 问题解决
slug: GitHub push超时 问题解决
date: 2022-12-04 11:47:00+0000
categories:
       - question_resolved
  tags:
       - github
---

```cmd  
22:43:27.893: [tangzekk.github.io] git -c credential.helper= -c core.quotepath=false -c log.showSignature=false add --ignore-errors -A -- content/categories/daliy/_index.md
22:44:08.555: [tangzekk.github.io] git -c credential.helper= -c core.quotepath=false -c log.showSignature=false add --ignore-errors -A -f -- content/categories/daliy/_index.md
22:44:08.656: [tangzekk.github.io] git -c credential.helper= -c core.quotepath=false -c log.showSignature=false commit -F C:\Users\kk\AppData\Local\Temp\git-commit-msg-.txt --
[master e67c347] first test
 1 file changed, 10 insertions(+)
 create mode 100644 content/categories/daliy/_index.md
22:44:10.386: [tangzekk.github.io] git -c credential.helper= -c core.quotepath=false -c log.showSignature=false push --progress --porcelain origin refs/heads/master:master
fatal: unable to access 'https://github.com/tangzekk/tangzekk.github.io.git/': OpenSSL SSL_read: Connection was aborted, errno 10053
22:44:46.748: [tangzekk.github.io] git -c credential.helper= -c core.quotepath=false -c log.showSignature=false push --progress --porcelain origin refs/heads/master:master
fatal: unable to access 'https://github.com/tangzekk/tangzekk.github.io.git/': Failed to connect to github.com port 443 after 21112 ms: Timed out

```

### 解决方案

git命令全部走本地代理,需要代理软件

```cmd
git config --global http.proxy socks5 127.0.0.1:7890 
git config --global https.proxy socks5 127.0.0.1:7890 

git config --global http.proxy 127.0.0.1:7890 
git config --global https.proxy 127.0.0.1:7890

```，,