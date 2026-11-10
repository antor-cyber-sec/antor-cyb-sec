# Day 7: LAN, WAN, Router, Switch and Default Gateway

## What I learned
- A LAN is a small local network, like my home Wi-Fi. It is like a corridor inside a building.
- A WAN is a large outside network. The internet is the biggest WAN. It is like the roads of a whole city.
- A router connects the LAN to the WAN and decides where data goes. It also does NAT.
- A switch connects devices inside the same LAN. It sends data only to the right device, like a postman who delivers to the correct door only.
- The default gateway is where my computer sends traffic first when the destination is outside the LAN. Usually it is the router.
- DHCP automatically gives a device its IP address (and also tells it the gateway and DNS server).

## My home network
```text
[Phone] ----\
             \
[Laptop] ----- [Router 192.168.x.x] ----- Internet (WAN)
             /
[Other devices]
|<------- LAN ------->|<-------- WAN -------->|
```

## Hands-on practice
All commands were run on my own computer.

**1. `ipconfig /all`**
- Most adapters showed "Media disconnected". Only the Wi-Fi adapter was active.
- Default Gateway: 192.168.x.x
- DHCP Enabled: Yes
- DHCP Server and DNS Server were both the same address as my gateway, so my router does several jobs.
- DHCP gives the IP for a limited time (a lease), then renews it.

**2. Comparison with `tracert`**
- The first hop in my earlier `tracert google.com` was the same address as my default gateway. So the first step of my traffic is always my own router.

**3. `ping` to the gateway**
- Average time: 2 ms 
- It is much faster than pinging 8.8.8.8 (about 26 ms) because the router is inside my home and Google's server is far away.

## Quiz self-check
Score: 4/4

> Note: All practice was done on my own computer using safe, legal commands. Full IP addresses are hidden on purpose.
