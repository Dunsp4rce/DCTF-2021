---
layout: post
title: "Very secure website"
author: "shreyas-sriram"
tags: ['Web']
---

Some students have built their most secure website ever. Can you spot their mistake?

[http://dctf1-chall-very-secure-site.westeurope.azurecontainer.io/](http://dctf1-chall-very-secure-site.westeurope.azurecontainer.io/)

## Solution
- The website contains the [source code]({{site.baseurl}}/assets/Very-secure-website/source-code)
- From the source code, it can be seen that the right combination of username and password will give the flag
- The hashing algorithm used is `tiger128,4`, which seems to be weak
- Crack the username hash `51c3f5f5d8a8830bc5d8b7ebcb5717df` (use [this website](https://md5hashing.net/hash/tiger128,4)) to get `admin`, however the password cannot be reversed
- Some research on using `equal-equal` and `tiger128,4` leads to [PHP magic hashes](https://github.com/spaze/hashes/blob/master/tiger128%2C4.md)
- Using `LnFwjYqB` as the password reveals the flag

## Flag
```
dctf{It's_magic._I_ain't_gotta_explain_shit.}
```
