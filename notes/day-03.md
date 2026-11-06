# Day 3: DNS (Domain Name System)

## What I learned
- DNS translates a domain name (like google.com) into an IP address.
- Think of it as the phone book of the internet: I use names, computers use numbers.
- A DNS server is a computer that stores these name-to-IP records. For example, 8.8.8.8 is Google's public DNS server.

## What happens when I type a website name in the browser
1. I type a domain name, for example google.com.
2. My computer asks a DNS server: "What is the IP address of google.com?"
3. The DNS server replies with the IP address.
4. My browser connects to that IP and loads the website.

## Key terms
- **A Record (Address Record):** a type of DNS record that maps a domain name to an IPv4 address. DNS has other record types too, which I will learn later.
- **DNS Cache:** a temporary memory on my computer that remembers recent DNS answers, so the computer does not need to ask again and again. This makes browsing faster.

## Hands-on practice
Commands I used on my own computer:

| Command | What it does |
|---|---|
| `nslookup google.com` | Shows the IP address(es) of a domain and which DNS server answered |
| `ping google.com` | Resolves the name to an IP first, then tests the connection and shows latency |
| `ipconfig /displaydns` | Shows the domain names stored in my computer's DNS cache |

Observations:
- `nslookup` showed two things: the DNS server that answered, and the IP address of the domain.
- Big websites can return more than one IP address, because they run many servers.
- `ping` showed the domain's IP address in its first line, and the latency in `time=` was 38 ms.
- I tested these domains: google.com, wikipedia.org, github.com, youtube.com

## Quiz self-check
Score: 4/4

## Next
Day 4: continue Networking basics.

> Note: All practice was done on my own computer using safe, legal commands.
