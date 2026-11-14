# What Happens When I Type github.com in My Browser?

A beginner-friendly walkthrough, based on what I learned in my first days of studying networking. I verified each step on my own computer using safe, legal commands.

## The 6 steps

| Step | What happens | Tool I used to see it |
|---|---|---|
| 1. DNS | My computer asks a DNS server for the IP address of github.com. | `nslookup github.com` |
| 2. Routing | My data goes to my default gateway (my router) and then across the internet, hop by hop. | `tracert`, `ipconfig /all` |
| 3. TCP handshake | My computer and the server agree to connect on port 443 (SYN, SYN-ACK, ACK). | `curl -v` (Connected to ... port 443) |
| 4. TLS handshake | The server shows its certificate and my browser checks it. We create a secret key and encrypt all further data. | Browser certificate viewer, `curl -v` |
| 5. HTTP request | My browser sends a GET request: "please give me this page". | Browser DevTools, `curl -v` |
| 6. HTTP response | The server replies with a status code (200 OK) and the page. The browser displays it. | Browser DevTools, `curl -v` |

## In one sentence
Look up the name, follow the path, connect, lock the connection, ask, receive.

## What I observed myself
- `nslookup github.com` returned an IP starting with 20.247. My DNS server was my router (my default gateway).
- `curl -vI https://github.com` connected on port 443 and the response status was 200 OK. It connected to a different IP (starting with 57.155) than nslookup, because large sites have many servers and DNS can return different addresses.

## Key concepts used
IP address, DNS, default gateway, port, TCP, TLS, HTTPS, HTTP methods and status codes.

## What I want to learn next
Linux, then web security basics.

> All practice was done on my own computer using safe, legal commands.
