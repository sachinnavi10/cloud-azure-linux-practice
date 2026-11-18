# Day 4 - Networking Fundamentals

Networking is extremely important for Azure administrators and cloud engineers. It helps diagnose connectivity, DNS, routing, and web-service issues.

## Networking topics

| No. | Topic | Practical command |
|---|---|---|
| 1 | IP address | `ipconfig` |
| 2 | DNS | `nslookup` |
| 3 | Network connectivity | `ping` |
| 4 | HTTP and HTTPS | `curl` |
| 5 | Network ports | `netstat` |
| 6 | Routing | `tracert` |

## First networking exercise

Open Git Bash and run the following commands.

### 1. Check your IP configuration

```sh
ipconfig
```

This displays your network adapter addresses, subnet masks, gateways, and DNS server information.

### 2. Check Google's DNS

```sh
nslookup google.com
```

This resolves `google.com` and shows the DNS server and returned IP addresses.

### 3. Test internet connectivity

```sh
ping -n 4 google.com
```

The `-n 4` option sends four echo requests. It tests whether the host is reachable and shows packet response times.

### 4. Check an HTTPS website

```sh
curl -I https://www.microsoft.com
```

This sends a HEAD request and displays the website's HTTP response headers.

## Additional networking commands

### View network connections and listening ports

```sh
netstat
```

### Trace the route to a destination

```sh
tracert google.com
```

This shows the network hops between your computer and the destination.

## HTTP and HTTPS

- HTTP sends web traffic without TLS encryption.
- HTTPS sends web traffic over TLS encryption.
- `curl -I` retrieves response headers from a web server.

## Practical assignment

Run these commands one by one in Git Bash:

```sh
ipconfig
nslookup google.com
ping -n 4 google.com
curl -I https://www.microsoft.com
netstat
tracert google.com
```
