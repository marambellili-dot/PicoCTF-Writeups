# Fantasy

## Category

General Skills

## Difficulty

Easy

## Description

A text-based game accessible through a remote server using Netcat.

The goal was to connect to the server, follow the instructions and obtain the flag.

## Tools Used

- Netcat (nc)
- Linux Terminal

## Connection

```bash
nc verbal-sleep.picoctf.net 65043
```

## Solution

1. Connected to the remote server using Netcat.
2. Read the game instructions.
3. Chose the appropriate options during the story.
4. Continued until the flag was displayed.

## Flag

```text
picoCTF{m1113n1um_3d1710n_8d7ec7f5}
```

## What I Learned

- How to connect to a remote service using Netcat.
- Basic client-server communication.
- Interacting with terminal-based applications.
- Reading and following challenge instructions carefully.

## Notes

Netcat is a networking utility that can establish TCP and UDP connections. It is commonly used for troubleshooting, testing network services and CTF challenges.