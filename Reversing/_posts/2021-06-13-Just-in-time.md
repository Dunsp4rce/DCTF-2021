---
layout: post
title: "Just-in-time"
author: "vishalananth"
tags: ['Reversing']
---

Don't fall in (rabbit) holes

**Files**
- [justintime]({{site.baseurl}}/assets/Just-in-time/justintime)

## Solution

Open the binary using Ghidra you can see the following functions:

```
func1() - Reads the same binary and stores the first 7 characters in a char* array, this will act as a key

encrypted flag - 0x1b263820796567487228246731624b757b226635604e7d74233333314e762f25603131462331

func2() - Takes the encrypted flag as input and performs char = 0xff % ((int)char + 0x25) for every character and then puts the result in a temporary string with the flag format dctf{}

func3() - Takes the encrypted flag and the key and performs an xor between the key(repeated to match length of the flag) and the encrypted flag.

func4() - Same as func2() but does char = 0xff % ((int)char + 0x30)
```

So on breaking and single stepping at different points, we discovered that functions 2 and 4 were rabbit holes since they did not really affect the encrypted flag. function 3 was called twice, since it did an xor, the first call decrypted the flag, the second call encrypted it back. So our goal was to break in between the 2 calls to obtain the decrypted flag before it was encrypted again.

I used the break statement to break inside the loop in func3() which performed the xor to retrieve the key. Once I had the key I did the xor between the encrypted flag and the key to obtain the flag

## Flag
```
dctf{df77dbe0c407dd4a188e12013ccb009f}
```