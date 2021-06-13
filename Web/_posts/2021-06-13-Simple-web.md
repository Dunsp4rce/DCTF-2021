---
layout: post
title: "Simple web"
author: "shreyas-sriram"
tags: ['Web']
---

Time to warm up!

[http://dctf1-chall-simple-web.westeurope.azurecontainer.io:8080](http://dctf1-chall-simple-web.westeurope.azurecontainer.io:8080)

## Solution
- The webpage contains a form with checkbox input field `I want flag!` (`flag`), however submitting the form with this option checked responds with `Not authorized`
- On closer inspection (pun intended), we find a hidden input field `auth`
- Send a request with both `flag` and `auth` set to `1` to get the flag in the response

## Flag
```
dctf{w3b_c4n_b3_fun_r1ght?}
```
