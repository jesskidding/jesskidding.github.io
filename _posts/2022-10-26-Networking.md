---
# Network Fundamentals
### 2022-10-26

---

We utilize the conventional **O**pen **S**ystems **I**nterconnection Model to explain computer networking concepts. Real-world networking uses the more compact TCP/IP paradigm, although the OSI model is simpler to grasp.

## Seven OSI layers:

#### Table of OSI layers: Application, Presentation, Session, Transport, Network, Data Link, Physical.

An OSI model mnemonic I prefer: **P**lease **d**o **n**ot **t**ouch **S**teve's **p**et **a**lligator.

Quick breakdown:

### Layer 7—Use:

* The OSI model's application layer gives computer programs networking possibilities. 
* It mostly interfaces with programs to convey data. 
* The presentation layer receives data from the application layer.

### Layer 6--Presentation:

* The application layer feeds the presentation layer. 
* The program usually understands this data, but the receiving computer's application layer may not. 
* The presentation layer encrypts, compresses, and formats data. 
* The session layer receives the data.

### Layer 5--Session:

* The session layer checks whether it can connect to the other computer over the network after receiving properly formatted data from the presentation layer. 
* If it can't, it returns an error and stops. 
* The session layer maintains sessions and synchronizes communications with the remote computer's session layer. 
* The communication-specific session created by the session layer is crucial. 
* This lets you make several queries to distinct endpoints at once without mixing up the data (like opening two tabs in a browser)! 
* Data is sent to Layer 4—the transport Layer—after the session layer successfully logs a host-remote connection.

### Layer 4--Transport:

* Transport layer functions are fascinating. It selects the data transmission protocol initially. TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the most used transport layer protocols. 
* TCP is connection-based, so computers create and maintain a connection for the request. The link ensures packet delivery, ensuring reliable transmission. 
* A TCP connection keeps the computers in continual contact to send data at a good pace and resend missing data. Instead, UDP throws data packets to the recipient machine, which must keep up (this is why a video transmission over something like Skype can be pixelated if the connection is bad). 
* TCP is used when accuracy is more essential than speed (e.g., file transfer or website loading), whereas UDP is used when speed is more critical (e.g. video streaming).

##### The transport layer breaks the transmission into segments (TCP) or datagrams (UDP), making it simpler to send the message.

### Layer 3—Network:

* Requests are routed via the network layer. 
* When you request information from a website on the Internet, the network layer takes the IP address and finds the optimal path. Logical addressing—IP addresses—is software-controlled at this point. Logical addresses categorize and arrange networks. 
* You're probably aware with IPV4, the most prevalent logical addressing format (i.e 192.168.1.1 is a common address for a home router).

### Layer 2—Data Link:

* Data link layer addresses transmission physical addressing. 
* It adds the receiving endpoint's physical (MAC) address to a network layer packet with the distant computer's IP address. 
* Network-enabled computers have NICs with MAC (Media Access Control) addresses.

#####  MAC addresses can be faked, but they're burned into the card by the manufacturer. The physical address determines where data is transmitted over a network.

##### Data link layers also prepare data for transmission.

##### When it gets data from layer 1, the physical layer, the data link layer examines it for corruption.

### Layer 1--Physical:

* Hardware is the physical layer. 
* This sends and receives network data transfer signals. 
* The physical layer converts binary data into signals and transmits them over the network. 
* It also receives signals and converts them back into binary data.


