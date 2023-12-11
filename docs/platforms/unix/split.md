---
layout: default
title: "split"
---

[🏠](/)
/ [docs](/docs)
/ [platforms](/docs/platforms)
/ [unix](/docs/platforms/unix)

## 📄 split

split - split a file into pieces

#### Synopsis

```sh
split [OPTION]... [FILE [PREFIX]]
```

Output  pieces of `FILE` to `PREFIXaa`, `PREFIXab`, ...; default size is 1000
lines, and default `PREFIX` is `x`.

With no `FILE`, or when `FILE` is `-`, read standard input.

#### Description

`-b SIZE`

The `SIZE` argument is an integer and  optional  unit  (example:  10K  is
10\*1024).

**Unix** Units are K,M,G,T,P,E,Z,Y  (powers  of 1024) or KB,MB,...  
(powers of 1000).

**macOS** Units are m or b.

#### Examples

```sh
tar zcf - content | split -b 1024m - cloudbackup.tar.gz.
```

join/untar with decompression:

```sh
cat cloudbackup.tar.gz.* | tar zxvf -
```

#### See Also

[📄 tar](tar.html)  

