# Week 13
12/08/14

## Amazon Web Services

### Announcments
- Tomorrow at 2pm - Secure Drop Certification Organization
- Most secure drops on the West Coast -- workshop on East Coast

### Ping and Traceroute
#### Ping
- Example: `ping google.com`
	- What we're seeing: response times:
```
64 bytes from 74.125.228.4: icmp_seq=68 ttl=54 time=14.511 ms
64 bytes from 74.125.228.4: icmp_seq=69 ttl=54 time=11.962 ms
64 bytes from 74.125.228.4: icmp_seq=70 ttl=54 time=13.684 ms
64 bytes from 74.125.228.4: icmp_seq=71 ttl=54 time=13.682 ms
64 bytes from 74.125.228.4: icmp_seq=72 ttl=54 time=13.845 ms
``` 
- "google.com" is not actually the DNS address, this is the ping adress.
- What we see is "latency time;" the time it takes to access the server
- `ping` is a quick way to tell whether or not you have a signal from the server
- To exit from `ping`, type `CTRL + C`
- When you send  a `ping` request, that request goes to a DNS server, translating "google.com" into a dns address. There is a travel time to DNS server; to minimize that trip lengthy, your computer searches out the closes DNS server
- Google has made their server strategically placed in the network to reduce latency time.

#### Traceroute
- `traceroute google.com` will output the number of connections and where the request is being forwarded to:
```
1  cc-wlan-1-vlan3502-1.net.columbia.edu (160.39.132.2)  16.243 ms  16.617 ms  4.318 ms
 2  phi-core-1-x-cc-wlan-1.net.columbia.edu (128.59.255.225)  3.308 ms  1.107 ms  1.128 ms
 3  cc-core-1-x-phi-core-1.net.columbia.edu (128.59.255.17)  1.082 ms  1.029 ms  1.011 ms
 4  nyser32-gw-1-x-cc-core-1.net.columbia.edu (128.59.255.6)  1.408 ms  1.945 ms  1.855 ms
 5  te0-2-1-2.rcr22.jfk01.atlas.cogentco.com (38.122.8.209)  1.946 ms  1.905 ms  3.830 ms
 6  be2356.ccr42.jfk02.atlas.cogentco.com (154.54.43.97)  4.996 ms  2.845 ms *
 7  be2151.mpd22.dca01.atlas.cogentco.com (154.54.40.73)  11.187 ms
    be2149.ccr22.dca01.atlas.cogentco.com (154.54.31.125)  9.279 ms  10.382 ms
 8  be2177.ccr41.iad02.atlas.cogentco.com (154.54.41.205)  10.074 ms  10.776 ms
    be2112.ccr41.iad02.atlas.cogentco.com (154.54.5.233)  10.257 ms
 9  38.88.214.50 (38.88.214.50)  9.565 ms  11.830 ms  9.244 ms
10  209.85.252.46 (209.85.252.46)  10.483 ms  31.646 ms  16.488 ms
11  72.14.238.173 (72.14.238.173)  12.111 ms  10.971 ms  10.963 ms
12  iad23s05-in-f4.1e100.net (74.125.228.4)  10.993 ms  11.147 ms  10.846 ms
```
- What do different latency times tell us?
	- The different tiers of internet providers: tier 1 own the network, higher numbers must lease server space.
	- NB: at a university, the traceroute between us and cogentco.com (a tier 1 provider) is much closer than on a home connection (because)
	- Length to server in, say, Russia or China is significally longer because traffic has to be routed much further.
	- If we try yandex.ru, we see many of the server locations masked. Russia is known for doing packet-sniffing.
- Traceroute allows us to analyze the structure of servers
- How we can use traceroute to learn what is censored?
	- Berkman Center will log into a server from China and, from the chinese server, ping NYTIMES -- this gives us realtime data on internet censorship
	- Sometimes it is an entire domain, sometimes it is a subdomain
	- A server knows where to pass the package. Packet-sniffing can look at the destination of packets and block packets whose location are say, controversial


## SSH and servers
- Secure Shell (SSH) is a network protocal for secure data encryption
- Programs like Transmission Control Protocol (TCP) and other Internet protocol (IP) suites divide up things into protocols. For example, email will be divided up among different protocols
- `ssh` is different; 
	- It establishes a "tunnel," a one-to-one connection 
	- Not divided into random packets, but instead, a stream.
	- Creates a secured and encrypted session to transmit data
- `ssh` is powerful, you can set up a session in Amazon, establish a secure connection, and then be able to transmit a connection to, say, a blocked site.
- This equivalent to VPN
- SSH commands:
	- `ssh -i [path to key] [address of server]`
	- In order for the key to work, its permissions must be set to rx -- -- (permissions for only the user, no other groups)
	- Your key will not work if it has any insecure permissions
	- `chmod go-rw [keyfile]` will remove group permisssions
		- ex: `chmod go-rw test.pem`

### On Free Speech
- Free speech is not free
- Free speech has a material substratum
- How does "freedom" manifest itself literally?
- We know how to describe free speech in "analog" forums (eg, in soapboxes, in political forums, in print newspaper) but in order to be informed citizens we need to know how free speech (and censorship) operate in digital spaces. 
- Zooming out - "Coding in Context" attempts to integrate computational knowledge in the Core