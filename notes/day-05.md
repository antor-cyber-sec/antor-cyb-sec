# Day 5: HTTP Basics

## What I learned
- HTTP is a request and response conversation between a browser and a server.
- Like ordering at a restaurant: the browser (customer) sends a request (order),
  and the server (waiter) sends back a response (food, or "not available")

## Methods
| Method | Purpose |
|---|---|
| GET | Retrieve data |
| POST | Send data |

## Status codes
| Code | Meaning |
|---|---|
| 200 | OK |
| 301 | Redirect |
| 304 | Not Modified (use cached copy) |
| 403 | Forbidden |
| 404 | Not Found |
| 500 | Server Error |

## Hands-on practice
- Used browser DevTools (F12 → Network) on example.com.
- Observed: example.com used GET. At first the status was 304 Not Modified because my browser had a cached copy. With "Disable cache" on, it showed 200 OK.
- Triggered a 404 by opening a page that does not exist on GitHub. DevTools showed GET and 404 Not Found.
- Used `curl -I https://example.com` and saw HTTP/1.1 200 OK in the response headers.

## Quiz self-check
Score: 4/4
