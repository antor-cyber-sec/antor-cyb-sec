# Day 9: Networking Capstone

## What I did
I connected everything from days 1-8 by answering one question: what happens when I type github.com in my browser? The full write-up is in my mini project:

- [What Happens When I Type github.com in My Browser?](../projects/how-a-website-loads.md)

## The 6 steps in short
DNS lookup, routing through my default gateway, TCP handshake (port 443), TLS handshake, HTTP request, HTTP response.

## Hands-on practice
- `nslookup github.com` returned an IP starting with 20.247. `curl -vI https://github.com` connected to a different IP (starting with 57.155), because large sites have many servers.
- `curl` showed the connection on port 443 and `200 OK`.

## Quiz self-check
Score: 3.5/4
- I mixed up HTTP's job (request and response) with its port and security. HTTP's job is that the browser asks for a page and the server replies.

> All practice was done on my own computer using safe, legal commands.
