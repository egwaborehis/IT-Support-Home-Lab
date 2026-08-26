# Test 03 — Networking Fundamentals & Diagnostics

## Overview

This test was created to practise basic networking and troubleshooting skills that could be useful in an IT support or help desk environment.

The aim was not just to run a few commands, but to understand what each command does, why it is useful, and how the results can help identify where a network problem might be coming from.

During the test I checked my computer's network configuration, tested the connection to my own computer, tested the connection to my router, tested external internet connectivity, checked DNS resolution and then tested connectivity using a domain name.

The main tools used were Windows Command Prompt commands:

```text
ipconfig
ping
nslookup
```

---

# 1. Checking the Network Configuration

## Objective

The first step was to find out how my computer was currently connected to the network.

I used:

```text
ipconfig
```

This displays information about the computer's network adapters and their current configuration.

I looked specifically at the Wi-Fi adapter and identified:

- IPv4 address
- Subnet mask
- Default gateway

### Results

| Network information | Result |
|---|---|
| IPv4 address | `192.168.1.X` |
| Subnet mask | `255.255.255.0` |
| Default gateway | `192.168.1.XXX` |

The exact IPv4 address and default gateway have been replaced with `X`/`XXX` in the public evidence because this project is stored on a public GitHub repository.

### Evidence

[View the network configuration screenshot](ipconfig-network-configuration.png)

---

## Understanding the IPv4 Address

The computer was using a private IPv4 address beginning with:

```text
192.168.1.X
```

An IPv4 address allows devices to identify and communicate with each other over an IP network.

On a home network, the router normally assigns private IP addresses to connected devices automatically using DHCP.

For example, different devices on the same network could have addresses such as:

```text
192.168.1.10
192.168.1.20
192.168.1.30
```

The exact address assigned to a device can change depending on the network's DHCP configuration.

---

## Understanding the Subnet Mask

The subnet mask found on the computer was:

```text
255.255.255.0
```

This is also known as a `/24` network.

The local network can therefore be represented as:

```text
192.168.1.0/24
```

The subnet mask helps the computer determine which devices are on the same local network and which destinations need to be reached through the default gateway.

For this network, devices would generally use addresses within the `192.168.1.x` range.

I do not need to memorise the binary calculation behind the subnet mask at this stage. The important practical point is understanding that the subnet mask helps determine whether another IP address is local or needs to be reached through the router.

---

## Understanding the Default Gateway

The default gateway was another `192.168.1.x` address.

In this environment, the default gateway is the BT Hub/router.

The default gateway is important because it provides the route for traffic that needs to leave the local network.

A simplified version of the connection is:

```text
My laptop
192.168.1.X
     |
     | Wi-Fi
     v
BT Hub / Router
192.168.1.XXX
     |
     v
Internet
```

This means that if my computer needs to communicate with something outside the local network, the traffic can be sent to the router.

---

# 2. Why Network Troubleshooting Should Be Done in Stages

One of the main things I learned from this test is that a user saying:

> "My internet isn't working."

does not necessarily mean that the internet itself is the problem.

There are several different points where a connection can fail.

For example:

- The computer's own networking system could have a problem.
- The Wi-Fi connection could be unavailable.
- The computer might not be able to reach the router.
- The router might be reachable but have no internet connection.
- DNS could be failing.
- A particular website or service could be unavailable.

Because of this, it is useful to test the connection in stages instead of immediately changing settings or reinstalling things.

The general troubleshooting path I followed was:

```text
My computer
     ↓
Local TCP/IP networking
     ↓
Local router
     ↓
Internet
     ↓
DNS
     ↓
Domain connectivity
```

Each test provides another piece of information about where a possible problem could be.

---

# 3. Testing the Local TCP/IP Stack

## Command

```text
ping 127.0.0.1
```

## What is 127.0.0.1?

`127.0.0.1` is the IPv4 loopback address.

It refers back to the computer itself.

This means that the test does not need to communicate with the Wi-Fi router or the wider internet.

Instead, it checks whether the computer's local TCP/IP networking functionality is responding.

## Result

The test returned successful replies.

The result was:

- Successful replies
- 0% packet loss
- Response time below 1 ms

## What this tells me

The successful result indicates that the computer's local TCP/IP networking stack was functioning correctly during the test.

This is useful as a first troubleshooting step because it checks the computer itself before investigating the rest of the network.

If this test had failed, I would investigate the computer's networking configuration and TCP/IP functionality before assuming that the router or internet connection was responsible.

---

# 4. Testing the Default Gateway

## Command

I then tested the default gateway that I identified using `ipconfig`.

The actual address has been redacted from the public evidence.

```text
ping [default gateway]
```

## Why test the gateway?

This checks whether my computer can communicate with the local router.

The test therefore moves one step further than the previous test:

```text
My computer
     |
     ↓
Wi-Fi connection
     |
     ↓
BT Hub / Router
```

## Result

The gateway responded successfully.

The result was:

- Successful replies
- 0% packet loss
- Average response time of approximately 2 ms

## What this tells me

The successful response indicates that my computer was able to communicate with the local BT Hub/router.

This provides evidence that the local network connection was working during the test.

If the `127.0.0.1` test worked but the gateway test failed, I would investigate things such as:

- Wi-Fi connection
- Ethernet connection
- Network adapter
- Network configuration
- Network drivers
- Router availability

This would help narrow the problem down to the connection between the computer and the local network rather than immediately blaming the wider internet.

---

# 5. Testing External Internet Connectivity

## Command

```text
ping 1.1.1.1
```

## Why use an IP address?

This test was slightly different because I used a public IP address rather than a domain name.

This is useful because it tests internet connectivity without depending on DNS.

For example:

```text
ping 1.1.1.1
```

does not require the computer to translate a domain name such as `google.com` first.

This means I can test whether the computer can reach an external destination separately from whether DNS is working.

## Result

The test returned successful replies.

The result was:

- Successful replies
- 0% packet loss
- Average response time of approximately 10 ms
- Maximum response time of approximately 11 ms

## What this tells me

The successful result indicates that my computer could reach an external internet destination.

When combined with the successful gateway test, the results provide evidence that the following connection was working:

```text
My computer
     ↓
BT Hub / Router
     ↓
Internet
```

---

# 6. Understanding DNS

## What is DNS?

DNS stands for:

**Domain Name System**

Computers communicate using IP addresses, but people normally use domain names because they are easier to remember.

For example:

```text
google.com
```

is much easier to remember than a numerical IP address.

DNS allows the computer to translate a domain name into an IP address.

A simplified process looks like this:

```text
google.com
     ↓
DNS lookup
     ↓
IP address
     ↓
Computer communicates with destination
```

This is why DNS is important when troubleshooting websites and other services.

It is also possible for internet connectivity to work while DNS has a problem.

For example:

```text
ping 1.1.1.1
```

could work while:

```text
google.com
```

cannot be resolved.

That would make DNS an important area to investigate.

---

# 7. Testing DNS Resolution

## Command

```text
nslookup google.com
```

## Purpose

I used `nslookup` to check whether my computer could resolve the domain name `google.com` into IP addresses.

## Result

The command successfully returned information for:

```text
google.com
```

The DNS server shown by my system was:

```text
bthub.home
```

The exact DNS server address was redacted from the public evidence.

The lookup returned multiple IP addresses.

Some of the returned addresses contained only numbers, which are IPv4 addresses, while others contained letters and numbers, which are IPv6 addresses.

### Evidence

[View the DNS lookup screenshot](nslookup-google.png)

---

## What "Non-authoritative answer" means

The `nslookup` result also displayed:

```text
Non-authoritative answer
```

This is not an error.

It does not mean that DNS is broken or that the result is unreliable.

It means that the server that responded to my request was not the authoritative DNS server that owns the original DNS records for `google.com`.

The local BT Hub can forward or cache DNS requests and return the information to the computer.

## What this tells me

The successful `nslookup` result shows that DNS resolution was working during the test.

My computer was able to ask for information about `google.com` and receive IP addresses in response.

---

# 8. Testing a Domain Name

## Command

```text
ping google.com
```

This was the final connectivity test.

## Why is this different from pinging 1.1.1.1?

When I ran:

```text
ping 1.1.1.1
```

the computer already had the destination IP address.

When I ran:

```text
ping google.com
```

the computer first needed to resolve `google.com` using DNS before it could communicate with the destination.

This means the test combines:

1. DNS resolution
2. Network connectivity

It therefore provides another useful check that both parts are working.

## Result

The command successfully returned replies.

The results were:

- 4 successful replies
- 0% packet loss
- Minimum response time of approximately 10 ms
- Maximum response time of approximately 12 ms
- Average response time of approximately 10 ms

The returned addresses included IPv6 addresses.

## What this tells me

The successful result indicates that:

- `google.com` could be resolved.
- The computer could communicate with the resolved destination.
- No packet loss was observed during the test.
- DNS and network connectivity were functioning during the test.

---

# 9. Complete Diagnostic Results

| Diagnostic | Command | Result | What it tested |
|---|---|---|---|
| Local TCP/IP | `ping 127.0.0.1` | PASS | Local networking stack |
| Default gateway | `ping [gateway]` | PASS | Computer → router |
| Internet connectivity | `ping 1.1.1.1` | PASS | External internet connection |
| DNS resolution | `nslookup google.com` | PASS | DNS functionality |
| Domain connectivity | `ping google.com` | PASS | DNS + network connectivity |

### Evidence

[View the ping connectivity tests](ping-connectivity-tests.png)

---

# 10. How I Would Use These Tests in IT Support

The main purpose of this exercise was not just to prove that my own internet works.

It was to understand how these commands could be used if a user reported a connectivity problem.

For example, if someone contacted the IT help desk and said:

> "My computer has no internet."

I could approach the problem systematically rather than immediately changing settings.

A possible investigation would be:

```text
1. Check the network configuration
        ↓
2. Test the local TCP/IP stack
        ↓
3. Test the default gateway
        ↓
4. Test an external IP address
        ↓
5. Test DNS
        ↓
6. Test the required domain/service
```

The result of each test would help determine where to investigate next.

---

## Example: Local TCP/IP Failure

If:

```text
ping 127.0.0.1
```

failed, I would investigate the computer's local networking functionality.

This would suggest that the problem could be closer to the computer itself rather than immediately assuming that the router or internet was responsible.

---

## Example: Gateway Failure

If:

```text
ping 127.0.0.1       PASS
ping [gateway]       FAIL
```

the computer's local networking stack would appear to be working, but communication with the router would not.

I would then investigate things such as:

- Wi-Fi connection
- Ethernet connection
- Network adapter
- Network driver
- IP configuration
- Router availability

---

## Example: Internet IP Failure

If:

```text
ping 127.0.0.1       PASS
ping [gateway]       PASS
ping 1.1.1.1         FAIL
```

the computer could communicate with the router, but could not reach the external destination.

I would then investigate areas such as:

- Router internet connection
- ISP connection
- Router configuration
- Wider network outage

---

## Example: DNS Failure

If:

```text
ping 1.1.1.1        PASS
nslookup google.com FAIL
```

the computer could reach an external IP address but could not resolve a domain name.

This would make DNS a strong area to investigate.

---

## Example: A Single Website Fails

If DNS worked and other internet tests worked but one particular website or service did not, I would not automatically assume that the user's entire internet connection was broken.

Further investigation could include:

- The specific website/service
- Browser problems
- Website availability
- Firewall or security software
- Cached DNS information
- Application-specific problems

This demonstrates why running several different tests is more useful than simply asking whether the user is "connected to Wi-Fi."

---

# 11. What I Learned

This test helped me understand that networking troubleshooting should be approached in a logical order.

The most important lesson was that a network problem can exist at different points.

For example:

```text
Computer
   ↓
Network adapter / connection
   ↓
Router
   ↓
Internet
   ↓
DNS
   ↓
Specific website or service
```

Testing these areas separately makes it easier to narrow down the cause of a problem.

I also gained practical experience using:

- `ipconfig`
- `ping`
- `nslookup`

I learned what an IPv4 address, subnet mask and default gateway are used for, as well as the difference between testing an IP address directly and testing a domain name.

I also learned that `Non-authoritative answer` in `nslookup` does not mean that DNS has failed.

---

# 12. Privacy and Evidence Handling

Because this project is stored on a public GitHub repository, I reviewed the screenshots before uploading them.

The exact private IPv4 address and default gateway were replaced with placeholders such as:

```text
192.168.1.X
192.168.1.XXX
```

The DNS server address was also redacted.

The purpose of the redaction was to protect unnecessary local network information while still providing enough evidence to demonstrate the work that was completed.

The original unredacted screenshots are kept privately and are not part of the public repository.

---

# 13. Conclusion

The networking diagnostic test was completed successfully.

The computer was able to:

- Identify its IPv4 configuration
- Identify its subnet mask
- Identify its default gateway
- Communicate with its own TCP/IP stack
- Communicate with the local BT Hub/router
- Reach an external internet destination
- Resolve a domain name using DNS
- Communicate with a destination using its domain name

No network or DNS fault was identified during the investigation.

More importantly, the exercise provided practical experience with a basic troubleshooting process that could be used in an IT support environment.

Instead of simply assuming that a user has an "internet problem", I now understand how to use several small tests to narrow down whether the issue is likely to be with the computer, local network, router, internet connection, DNS or a specific service.

This provides a useful foundation for more advanced networking, cloud engineering, DevOps and infrastructure work in the future.
