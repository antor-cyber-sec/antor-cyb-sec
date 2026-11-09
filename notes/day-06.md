# Day 6: TCP and UDP

## What I learned
- TCP is reliable. It confirms the connection first (three-way handshake) and resends lost data. It is like a phone call: both sides confirm they can hear each other before talking.
- UDP is fast but gives no guarantee that data arrives. It is like a loudspeaker announcement: the sender does not check who heard it.
- DNS usually uses UDP because its questions and answers are very small, so a handshake is not worth the extra time.

## Three-way handshake
1. SYN: the client asks to start a connection ("Hello")
2. SYN-ACK: the server agrees ("Hello, I can hear you, can you hear me?")
3. ACK: the client confirms ("Yes, I can hear you")

## TCP vs UDP
| | TCP | UDP |
|---|---|---|
| Reliability | Yes | No |
| Speed | Slightly slower | Faster |
| Analogy | Phone call | Loudspeaker |
| Examples | HTTP/HTTPS, SSH, FTP | DNS, video calls, online games |

## Hands-on practice
All commands were run on my own computer.

**1. `netstat -an`**
- TCP entries show states like LISTENING and ESTABLISHED.
- UDP entries have no state, because UDP has no connection.

**2. `tracert google.com`**
- The route had 7 hops.
- Hop 1 was my own router (a 192.168.x.x private address). Hops 2-5 were private addresses inside my ISP network (10.x.x.x). The last hops were Google's network.
- Latency grew from about 3 ms at the first hops to about 35 ms at Google.

**3. `ping -n 10 8.8.8.8`**
- Sent 10, received 9, lost 1 (10% loss).
- Round trip time: minimum 25 ms, maximum 32 ms, average 26 ms.
- One request timed out. Occasional loss in a short test is normal.

## Quiz self-check
Score: 3.5/4

## Key takeaways
- TCP = reliable, UDP = fast.
- `tracert` shows the path from my computer to a destination, one hop at a time.
- Packet loss shows how many packets did not arrive.

> Note: All practice was done on my own computer using safe, legal commands.
