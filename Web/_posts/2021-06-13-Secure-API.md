---
layout: post
title: "Secure API"
author: "shreyas-sriram"
tags: ['Web']
---

Frontend is overrated! API rocks! [http://dctf1-secure-api.westeurope.azurecontainer.io:8080](http://dctf1-secure-api.westeurope.azurecontainer.io:8080)

## Solution
- The website greets with

```
{"Error":"Authorization header not found! Try to login with guest credentials."}
```

- Login with `guest:guest` at [http://dctf1-chall-secure-api.westeurope.azurecontainer.io:8080/login](http://dctf1-chall-secure-api.westeurope.azurecontainer.io:8080/login) (ctfs aka take-a-guess, duh)
- A JWT token is received in the response
- Making an authenticated request to [http://dctf1-chall-secure-api.westeurope.azurecontainer.io:8080/](http://dctf1-chall-secure-api.westeurope.azurecontainer.io:8080/) returns the following response

```
{"Message":"Hi, guest! You are not admin, I have no secret for you."}
```

- Crack the JWT token with [https://github.com/ticarpi/jwt_tool](https://github.com/ticarpi/jwt_tool) or **hashcat** to get the secret

```
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzUxMiJ9.eyJ1c...z_BebT2HRYahSpjsbAyWlmdiNrxc6wAsg12ecsreUqQ:147852369
```

- Modify the JWT to impersonate as `admin` to get the flag

## Flag
```
dctf{w34k_k3y5_4r3_n0t_0k4y}
```
