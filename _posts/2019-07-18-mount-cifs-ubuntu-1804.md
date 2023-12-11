---
layout: default
title: "Mount CIFS on Ubuntu 18.04"
categories: [Unix]
author: "Stephen Quan"
tags: [JavaScript]
---

I posted on [https://askubuntu.com/a/1159138/327700](https://askubuntu.com/a/1159138/327700) instructions for mounting Windows shares on Ubuntu 18.04:

```bash
# /etc/fstab
\\contoso\share /mnt/share cifs vers=1.0,credentials=/root/.smb
```

```bash
# /root/.smb
username=billgates
password=secret
domain=microsoft
```
