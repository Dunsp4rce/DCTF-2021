---
layout: post
title: "DevOps vs SecOps"
author: "shreyas-sriram"
tags: ['Web']
---

Automatization is amazing when it works, but it all comes at a cost... You have to be careful...

(URL not missing)

## Solution
- While solving `Leak Spin` challenge, another repository was found in [DragonSec's GitHub page](https://github.com/DragonSecSI) - [DCTF1-chall-devops-vs-secops](https://github.com/DragonSecSI/DCTF1-chall-devops-vs-secops)
- The `main branch` did not have anything interesting, however there was another branch - [devops](https://github.com/DragonSecSI/DCTF1-chall-devops-vs-secops/tree/devops)
- The `workflow files` were using another repository - [DragonSecSI/.github](https://github.com/DragonSecSI/.github)
- One of the files in the repository contains the flag - [setup.py](https://github.com/DragonSecSI/.github/blob/main/setup.py)

## Flag
```
dctf{H3ll0_fr0m_1T_guy}
```
