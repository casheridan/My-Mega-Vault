## The OSI Model: An Overview
---
- The OSI (**O**pen **S**ystems **I**nterconnection) Model:
	- A model used to demonstrate the theory behind computer networking. 

Although the real world uses the more compact TCP/IP model. However, the OSI model, in many ways, is easier to get an initial understanding from.

The OSI model consists of seven layers:
| <u>OSI</u>   |
| ------------ |
| Application  |
| Presentation |
| Session      |
| Transport    |
| Network      |
| Data Link    |
| Physical     |

A mnemonic device that can be used for it can be:
- **A**nxious
- **P**ale
- **S**hakespeare
- **T**reated
- **N**ervous
- **D**runks
- **P**atiently

<u>Layer 7 -- Application:</u>
- Provides an network options for programs on the computer
- Works almost exclusively with applications
- Provides an interface to transmit data
- When data is recieved in the Application Layer it's passed to the Presentation layer

<u>Layer 6 -- Presentation:</u>
The presentation layer receives data from the application layer. This data tends to be in a format that the application understands, but it's not necessarily in a standardised format that could be understood by the application layer in the _receiving_ computer. The presentation layer translates the data into a standardised format, as well as handling any encryption, compression or other transformations to the data. With this complete, the data is passed down to the session layer.
- Presentation layer recieves data from Application layer
- Data is usually in a format application understands but not in a standardised format that the recieving computer understands
- Presentation layer translates data into standardised format, handles encryption, compression, and other transformations to the data
- Passes formatted data to Session layer

<u>Layer 5 -- Session:</u>
- Session layer recieves formatted data from the Presentation layer
- Session layer then makes session request with remote computer. If it can't then it will return an error. If it can then this layer's job is to maintain it and co-operate with the remote session in other to sync communications
- The session layer creates a unique session to the communication. This allows multiple reuqests to different endpoints simultaneously without mixup
- When session layer logs a successful connection between host and remote the data is passed to the Transport layer

<u>Layer 4 -- Transport:</u>
- Transport layer recieves data from Session layer
- Transport layer chooses which protocol to use to transmit the data. Two most common protocols are:
	- TCP (**T**ransmission **C**ontrol **P**rotocol):
		- Connection based
		- connection between computers is established and maintained for the duration of the request
		- **Allows for reliable transmission**
		- Ensures all packets get to the right place
		- Keeps computers in constant communication for acceptable speeds
		- Any data lost is re-sent
	- UDP (**U**ser **D**atagram **P**rotocol):
		- Throws packets of data all at once
		- If recieving computer can't keep up, it's their problem
			- Used in video applications and pixelated screens are a result of lost packets due to bad connection
	- Bottom line, TCP is used when accuracy is needed, UDP is used when speed is needed
- With the selected protocol the transport layer divides the transmission up into bite-sized pieces which makes it easier to transmit the message successfully.
	- TCP calls them *segments*
	- UDP calls them *datagrams*
- Transport layer passes data to network after protocol selection and transmission division

<u>Layer 3 -- Network:</u>
- Network layer recieves data from Transport layer
- Responsible for locating request destination using Logical addressing (i.e. IP addresses)
- Logical addresses are used to provide order to networks, catagorising them and allowing us to sort them.
- Most common form of logical addressing is IPV4 format (i.e. 192.168.1.1)
- Adds remote computer's Logical address to data and passes data to Data Link layer

<u>Layer 2 -- Data Link:</u>
The data link layer focuses on the _physical_ addressing of the transmission. It receives a packet from the network layer (that includes the IP address for the remote computer) and adds in the physical (MAC) address of the receiving endpoint. Inside every network enabled computer is a Network Interface Card (NIC) which comes with a unique MAC (Media Access Control) address to identify it.

MAC addresses are set by the manufacturer and literally burnt into the card; they can't be changed -- although they _can_ be spoofed. When information is sent across a network, it's actually the physical address that is used to identify where exactly to send the information.

Additionally, it's also the job of the data link layer to present the data in a format suitable for transmission.

The data link layer also serves an important function when it receives data, as it checks the received information to make sure that it hasn't been corrupted during transmission, which could well happen when the data is transmitted by layer 1: the physical layer.

- Data Link layer recieves data from Network layer and focuses on the *physical addressing* of the transmission
- Adds physical (MAC) address of the recieving endpoint
	- Every computer with a network contains a Network Interface Card (NIC), this comes with a MAC (Media Access Control) address to identify it
	- MAC addresses are physically burnt into the card by the manufacturer, they cannot be changed (but they *can* be spoofed)
	- When information is sent across a network it's uses the physical address to send the data to the exact machine
- It is also the job of the Data Link layer to present the data in a format suitable for transmission
- When recieving data the Data Link layer's job is to also make sure the recieved data hasen't been corrupted during transmission which can definetly happen when the data is passed to the Physical layer
- The data is passed to the physical layer with the recieving endpoint's MAC address

<u>Layer 1 -- Physical:</u>
- Physical layer recieves data from Data Link layer
- Physical layer transmits the data with the hardware of the computer. This is where the electrical pulses that make up data transfer over a network are sent and received.
- Physical layer converts the binary data of the transmission into electrical signals and transmits them across the network. Also responsible to recieving signals and converting them back into binary data

## Encapsulation
---

- As the data is passed down each layer of the model, more information containing details specific to the layer in question is added on to the start of the transmission.
- The Data Link layer also adds a piece on at the _end_ of the transmission
	- This *trailer* is used to verify that the data has not been corrupted on transmission
	- This adds increased security, as the data can't be intercepted and tampered with without breaking the trailer.
- This whole process is referred to as *encapsulation*
- Encapsulated data is given different names at different steps of the process
	- Layers 7, 6, and 5 the data is refered to as *data*
	- Layer 4 referes to the data as *segments*/*datagrams* (depending if TCP or UDP was selected as the transmission protocol)
	- Layer 3 the data is refered as a packet
	- Layer 2 the data becomes a frame
	- Layer 1 transmits the data as a frame
- The recieving computer reverses this practice (known as de-encapsulation)
- The processes of encapsulation and de-encapsulation are very important -- not least because of their practical use, but also because they give us a standardised method for sending data

## TCP/IP
---

The TCP/IP (Transmission Control Protocol/Internet Protocol) model is very similar to the OSI model and is generally used in the real-world.

The TCP/IP model has 5 layers:
- Application
- Transport
- Internet
- Network Interface

| OSI          | TCP/IP            |
| ------------ | ----------------- |
| Application  | Application       |
| Presentation | Application       |
| Session      | Application       |
| Transport    | Transport         |
| Network      | Internet          |
| Data Link    | Network Interface |
| Physical     | Network Interface |

TCP is a connection-based protocol, a stable connection must first form. This process of this connection formation is called the *three-way handshake*
- Client sends special request to remote Server indicating it wants to initialize a connection
- The request packet contains a SYN (synchronise)
- The Server responds with a packet containing the SYN bit as well as an ACK (acknowlegement) bit
- The Client then sends a packet containing the ACK bit, confirming the successful setup
- Data can then be reliably transmitted between the Client and Server
- Any data lost or corrupted is re-sent, appearing to be a lossless connection

![[Pasted image 20221028033228.png]]

## Ping
---

Ping is used to test if a connection to a remote resource is possible. Usually a website, but could also be a computer on a home network. Ping uses the ICMP protocol, which a slightly less known TCP/IP protocol. ICMP works on the network layer of the OSI model and Internet layer of the TCP/IP model.

Syntax: `ping [target]`

## Traceroute
---

Traceroute is a logical follow up to ping. This follows every intermediate step between the computer and the resource requested. The Windows traceroute uses ICMP by default, the same that ping uses. Unix on the other hand uses UDP by default. Both can be altered using switches.

Syntax: `traceroute [destination]`

## WHOIS
---

Whois allows you to query who a domain name is registered to. Everywhere except Europe redacts personal information and can get a great deal of research off of a whois search.

Syntax: `whois [domain]`