---
 # Active Reconnaissance
### 2022-12-04

---

## I
Any connection might record data in the logs that includes the client IP address, connection time, and duration, among other things.
Not all relationships, however, are unsavory.
You may make your ongoing reconnaissance seem like routine client activity.
Take online surfing as an example. Among hundreds of other genuine users, no one would notice a browser linked to a target web server.
When you are a member of the red team (attackers) and don't want to frighten the blue team, you may employ such strategies to your benefit (defenders).



## II


*A web browser may be used in a variety of ways to learn more about a topic.*


The browser establishes connections with the following:


When using HTTP to visit the website, TCP port 80 is used by default.

When using HTTPS to visit the website, TCP port 443 is used by default.


The web browser does not display the usual ports for HTTP and HTTPS, 80 and 443, in the address bar.
Custom ports may, however, be used to access a service.
For instance, https://127.0.0.1:8834/ will establish an HTTPS connection to localhost 127.0.0.1 at port 8834.
We will get a webpage if there is an HTTPS server listening on that port.


To launch the Developer Tools in Firefox while viewing a website, press Ctrl+Shift+I on a PC or Option + Command + I ( + + I) on a Mac.
You can launch Google Chrome or Chromium with similar shortcuts as well.
You may examine a variety of items that your browser has received and exchanged with the distant server using developer tools.
You may examine the cookies that have been placed on your computer, see the JavaScript (JS) files, and even edit them, as well as learn the site's organizational structure.


## III


A distant system receives a packet from the ping command, and the remote system responds.
By doing so, you may determine if the distant system is up and that the network connecting the two systems is operational.


Start using ping by typing ping MACHINE IP or ping HOSTNAME.
In the latter, before delivering the ping packet, the system must translate HOSTNAME into an IP address.
On a Linux machine, you must use CTRL+c to halt it if you don't provide the count.
So, if you just want to transmit ten packets, you may think about using the command ping -c 10 MACHINE IP.
On a Microsoft Windows machine, this is equal to ping -n 10 MACHINE IP.


Ping technically belongs to the ICMP protocol (Internet Control Message Protocol).
We are particularly interested in the ping (ICMP echo/type 8) and ping reply (ICMP echo reply/type 0) inquiries that ICMP provides.
It is not necessary to provide ICMP information in order to utilize ping.


There are many reasons why we may not have received a ping reply when we sent one, such as the following:


The target machine is not responding; it may be that it is still loading up, has been switched off, or that the OS has crashed.

It is not connected to the network, or a problematic network equipment is in the way.

Such packets are programmed to be blocked by a firewall.
The firewall might be an application running on the machine or a different network equipment.
Be aware that the MS Windows firewall by default disables ping.

Your computer is no longer connected to the network.


## IV


The traceroute command shows the path packets from your system to an other host travel.
Finding the IP addresses of the routers or hops that a packet travels through on its way from your system to a destination host is the goal of a traceroute.
This command also shows how many routers are in use between the two systems.
It is useful since it shows how many hops (routers) there are between your system and the destination host.
However, keep in mind that since many routers employ dynamic routing protocols that react to network changes, the path that the packets follow may vary.


The route from your system to a target system cannot be found in a straightforward manner.
To "trickle" the routers into disclosing their IP addresses, we depend on ICMP.
By including a modest Time To Live (TTL) in the IP header field, we may achieve this.
Though the T in TTL stands for time, TTL actually refers to the maximum number of routers or hops a packet may make before being discarded; it is not a measure of the total amount of time.


The TTL will be deleted, however, and an ICMP Time-to-Live exceeded message will be delivered to the original sender if it hits 0.
The system sent the following figure to the router with TTL set to 1.
The TTL is reduced by 1 by the first router along the path, arriving at 0.
As a result, the packet will be dropped by this router, and an ICMP time exceeded in-transit error message will be sent.
Be aware that certain routers are set up so they don't transmit these ICMP signals when they trash a packet.


On Linux, traceroute will begin by delivering IP packets with a TTL of 1 that include UDP datagrams.
As a result, the first router encounters a TTL=0 and responds with an ICMP Time-to-Live exceeded.
Consequently, a TTL of 1 will enable you to discover the first router's IP address.
The next packet it sends has a TTL of 2, and when it reaches the second router, it is dropped.
so on.


Depending on how long you run traceroute, there may be one or more hops or routers between your system and the destination system.
Even if you are on the same network or repeat the traceroute command quickly, there is no assurance that your packets will always take the same path.

A public IP address is sometimes returned by routers.
Depending on the breadth of the desired penetration testing, you could look at a number of these routers.

A few routers don't respond to requests.


## V


The TELNET (Teletype Network) protocol was created in 1969 to facilitate command-line interaction with distant systems (CLI).
For remote administration, the command telnet therefore makes use of the TELNET protocol.
Telnet uses port 23 by default.
Telnet transmits all information, including usernames and passwords, in cleartext, which is risky from a security standpoint.
Anybody with access to the communication channel might easily obtain the login information if it were sent in cleartext.
SSH (Secure SHell) protocol is a safe substitute.


The telnet client, however, may be used for various things because to its simplicity.
You may connect to any service and take its banner using Telnet since it uses the TCP protocol.
Unless it utilizes encryption, you may connect to any TCP-based service using telnet MACHINE IP PORT and even exchange a few messages.


Say we wish to learn more about a web server that is listening on port 80.
Using the HTTP protocol, we interact after establishing a connection with the server at port 80.
You just need to perform GET / HTTP/1.1; you don't need to go into the HTTP protocol.
With the GET /page.html HTTP/1.1 command, you may provide a different page than the standard index page.


A pentester may benefit greatly from the apps provided by etcat or simply nc.
TCP and UDP protocols are both supported by Netcat.
It may work as a server that listens on a port of your choosing, or it can work as a client that connects to a listening port.
As a result, it is a practical tool that can be used as a straightforward client or server across TCP or UDP.


You may connect to another system's listening port by using netcat to listen on a TCP port.


If you wish to open a port and listen on it on the server machine, you may use nc -lp 1234 or, better yet, nc -vnlp 1234, is similar to nc -v -l -n -p 1234.
As long as the port number is preceded immediately by -p, the letter order is irrelevant.


#### -l Listen mode
#### -p Enter port number
#### -n Numeric only; no hostname resolution with DNS
#### -v Verbose output (optional, yet useful to discover any bugs)
#### -vv very verbose (optional) 
#### -k keep listening when the client disconnects




Just before the port number you wish to listen on, the option -p should appear.

DNS lookups and warnings are avoided using the -n option.

To listen on a port smaller than 1024, root credentials are required.



Consider the case below.
We'll use port 1234 as a listening port on the server side.
The command nc -vnlp 1234 will help us do this (same as nc -lvnp 1234).
Since the listening server in our example has the IP address MACHINE IP, we can establish a client-side connection to it by running the command nc MACHINE IP 1234.
Whatever you enter on one side would be echoed on the other side of the TCP tunnel with this configuration.


## VI


You may use telnet to see whether ports are open and accessible by trying to connect to them, traceroute to map the route to the target, and ping to see if the target system replies to ICMP Echo.

#### ping     ping -c 10 MACHINE_IP on Linux or macOS
#### ping     ping -n 10 MACHINE_IP on MS Windows
#### traceroute     traceroute MACHINE_IP on Linux or macOS
#### tracert     tracert MACHINE_IP on MS Windows
#### telnet     telnet MACHINE_IP PORT_NUMBER
#### netcat as client     nc MACHINE_IP PORT_NUMBER
#### netcat as server     nc -lvnp PORT_NUMBER

Even though they are basic tools, they are easily accessible on the majority of platforms.
A web browser in particular may be a crucial tool in your toolbox for performing reconnaissance covertly as it comes pre-installed on almost all computers and smartphones. 


