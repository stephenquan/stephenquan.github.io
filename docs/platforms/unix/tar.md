---
layout: default
title: "tar"
---

[🏠](/)
/ [docs](/docs)
/ [platforms](/docs/platforms)
/ [unix](/docs/platforms/unix)

## 📄 tar

tar - an archiving utility

#### Synopsis

```sh
tar [-C folder] -[zv]cf ARCHIVE [FILE...]  
tar [-C folder] -[zv]xf ARCHIVE
tar [-C folder] -[zv]tf ARCHIVE
```

#### Details

`-C folder` change subfolder

`-z` use zLib compression

`-c` compress

`-t` list

`-v` verbose

`-x` extract

#### Examples

tar/split with compression:

```sh
tar -zcf - content | split -b 1024m - cloudbackup.tar.gz.
```

join/untar with decompression:

```sh
cat cloudbackup.tar.gz.* | tar -zvxf -
```

encrypt and archive content:

```sh
tar -zcf - content | openssl  enc -e -aes256 -out securebackup.tar.gz
```

decrypt and restore content:

```sh
openssl enc -d -aes256 -in securebackup.tar.gz | tar -zxf -
```

#### See Also

[📄 split](split.html)

