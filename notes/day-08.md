# Day 8: HTTPS and Encryption

## What I learned
- HTTP sends data in plain text, like an open letter. Anyone on the path (for example on public Wi-Fi) could read it.
- HTTPS is HTTP plus TLS (Transport Layer Security). Like a sealed envelope: people outside cannot see what is inside.
- TLS gives two things: encryption (data is scrambled so others cannot read it) and identity (proof that I am visiting the real site).
- A certificate is like an ID card for a website. A trusted Certificate Authority (CA) verifies it. It shows the site name, who issued it, and how long it is valid.
- Entering a password on an HTTP site on public Wi-Fi is dangerous, because someone in the middle can read it.

## How the TLS handshake works (simple)
1. The browser asks for a secure connection.
2. The site shows its certificate.
3. The browser checks it. If valid, both sides create a secret key.
4. All data is then encrypted with that key.

## Hands-on practice
All practice was done in my own browser and Command Prompt.

**1. Certificates I checked**
| Site | Issued by | Valid from | Valid until |
|---|---|---|---|
| github.com | Sectigo | Oct 30, 2026 | Jan 28, 2027 |
| *.google.com | Google Trust Services | Nov 3, 2026 | Jan 26, 2027 |
| *.wikipedia.org | Let's Encrypt | Oct 5, 2026 | Jan 3, 2027 |

- The three sites use three different Certificate Authorities.
- All three certificates are valid for only about 3 months.
- `*.google.com` is a wildcard certificate: it covers all subdomains of google.com.

**2. `curl -vI https://www.facebook.com`**
- The connection used port 443 (HTTPS).
- The output showed `schannel`, the Windows TLS library.
- Lines starting with `>` are my request, lines starting with `<` are the server's response (`HTTP/1.1 200 OK`).
- I also noticed `Set-Cookie` headers with `secure` and `httponly` flags. I will learn about them later.

## Quiz self-check
Score: 4/4

> Note: All practice was done on my own computer using safe, legal commands.
