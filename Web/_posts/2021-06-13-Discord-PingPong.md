---
layout: post
title: "Discord PingPong"
author: "shreyas-sriram"
tags: ['Web']
---

Our bot was able to infiltrate the server of our nemesis, but we don't know how to get the flag.

*A discord bot binary is provided*

## Solution
- On running the binary, the following is printed

```
Last message in #general is: Welcome to our secret server! Only trusted bots and users have access to the secret channels. Our secret plans have been moved from here to a secret channel.
Bot is now running.  Press CTRL-C to exit.
```

- To understand the bot's purpose, proxy the requests through Burp Suite
- The bot's auth token and channel ID is seen in the requests
- Enumerate the server with the bot's auth token to find guild ID and other channels which contain the flag
- Example request

```
GET /api/v9/guilds/838867536220127303/channels HTTP/1.1
Host: discord.com
User-Agent: DiscordBot (https://github.com/bwmarrin/discordgo, v0.23.0)
Authorization: Bot ODM4ODY3MDA4MTI3ODkzNTQ1.YJBVyA.zTQk10ZIQpMfT_Evi00sAkt5KIA
Accept-Encoding: gzip, deflate
Connection: close
```

## Flag
```
dctf{7h3_R0b0t_Upr151ng_15_NEAR!}
```
