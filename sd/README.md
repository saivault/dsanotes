<h1 align="center">System Design</h1>

<ul>
<li><a href="#intro" style="text-decoration:none">Introduction</a></li>
<li><a href="#df" style="text-decoration:none">Design Fundamentals</a></li>
<li><a href="#cs" style="text-decoration:none">Client-Server Model</a></li>
<li><a href="#np" style="text-decoration:none">Network Protocols</a></li>
<li><a href="#storage" style="text-decoration:none">Storage</a></li>
<li><a href="#landt" style="text-decoration:none">Latency And Throughput</a></li>
<li><a href="#avail" style="text-decoration:none">Availability</a></li>
<li><a href="#cache" style="text-decoration:none">Caching</a></li>
<li><a href="#proxy" style="text-decoration:none">Proxies</a></li>
<li><a href="#lb" style="text-decoration:none">Load Balancers</a></li>
<li><a href="#cs" style="text-decoration:none">Hashing</a></li>
<li><a href="#cs" style="text-decoration:none">Relational Databases</a></li>
<li><a href="#cs" style="text-decoration:none">Key-Value Stores</a></li>
<li><a href="#cs" style="text-decoration:none">Specialized Storage Paradigms</a></li>
<li><a href="#cs" style="text-decoration:none">Replication And Sharding</a></li>
<li><a href="#cs" style="text-decoration:none">Leader Election</a></li>
<li><a href="#cs" style="text-decoration:none">Peer-To-Peer Networks</a></li>
<li><a href="#cs" style="text-decoration:none">Polling And Streaming</a></li>
<li><a href="#cs" style="text-decoration:none">Configuration</a></li>
<li><a href="#cs" style="text-decoration:none">Rate Limiting</a></li>
<li><a href="#cs" style="text-decoration:none">Logging And Monitoring</a></li>
<li><a href="#cs" style="text-decoration:none">Publish/Subscribe Pattern</a></li>
<li><a href="#cs" style="text-decoration:none">MapReduce</a></li>
<li><a href="#cs" style="text-decoration:none">Security And HTTPS</a></li>
<li><a href="#cs" style="text-decoration:none">API Design</a></li>
</ul>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<br><br><br><br><br><br><br><br>
<div align="center">0</div>
<p id="intro">Where the coding interview serves primarily as an assessment of your problem-solving ability, the systems design interview is a test of your engineering knowledge veiled behind the facade of an open-ended design question.</p> 
<br><br>
If a coding interview problem is given to someone who has no coding background, no computer science background, they would likely be able to tackle the problem at least a little bit.They wouldn't be able to know that they have to use a certain data structure to solve a problem optimally. But they would be able to conceptually tackle the problem. <br>
With Systems Design interviews on the other hand, that would not be possible.If someone with no software engineeering background is given a canonical Systems Design interview question like design Youtube, design a website where millions of people can upload video content and billions of people can view that content and comment on it, like it, that person would not be able to answer this question properly. Because Systems Design interviews really do require a lot of knowledge about Systems, about how to build Robust, Functional, and Scalable Systems. <br>
That's where Design Fundamentals come into play.
<br><br>
<div align="center">
<b>Building scalable, production-ready applications is both art and science. </b>
</div>
<br>
Science, in that it requires knowledge of many topics in computer engineering; art, in that it demands an eye for making smart design choices and piecing together the right technologies.
<br><br>
<h2>How Systems Design interviews actually work?</h2>
System Design interview questions are very intentionally vague. A proposed solution to a system design interview question may very well not be objectively correct or objectively incorrect unlike with coding interviews.<br><br>
<b>Job:-</b> Justify your Solution.<br>
Explain to rationalise why you made certain choices, why you've designed parts of your system in one way instead of another, make your interviewer understand why your proposed solution is reasonable, why it's sound, and why it might be the best one. Or perhaps why it might not be the best one, why it might be one of many potential solutions.
<br><br><br><br><br><br><br><br><br><br><br><br><br>
<div align="center">1</div>
<h1 id="df">What are Design Fundamentals ?</h1>
Design Fundamentals are the foundational knowledge that is needed for Systems Design interviews just as Data Structures are the foundational knowledge that is needed for Coding Interviews.
<h2>Four categories of Design Fundamentals</h2>
<ul>
    <li>
        <b>Underlying (or) Fundamental Knowledge</b><br>
        Eg:- client-server architecture, network protocols
     </li>
    <li>
        <b>Key characteristics of systems</b><br>
        Things you might want a system to have, often involving trade offs. <br>
        Eg:- Availability, Latency, Throughput, Redundancy, Consistency
     </li>
     <li>
        <b>Actual components of a system</b><br>
        Tangible things that you can either have in a system or implement in a system. <br>
        Key components that are gonna allow your system to have the key characteristics that we just mentioned above. <br>
        Eg:- Load Balancer, Proxy, Cache, Rate Limiting, Leader Election
    </li>
    <li>
        <b>Actual technology</b><br>
        Real existing products/services that you can actually use in a system either as actual components or to achieve some characteristic in a system. <br>
        Eg:- nginx, Redis, Amazon S3, zookeeper, XCB, Google cloud storage
    </li>
</ul>
The fourth category of design fundamentals is the one that's often overlooked.
Also, this is very important one that can really round you off and make you shine in a Systems Design interview,

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
tangible - real, physical
<div align="center">2</div>
<h1 id="cs">Client-Server Architecture</h1>

- Foundation of the modern internet.
- Foundation of how computers speak to one another

For time being, lets consider some layman terminology. Client is some machine that speaks to the server. Server is another machine that listens to clients and speaks back to those clients. And when we use the word speak here, what we really mean is sending data. Client requests data from server and then the server returns it.<br>
The architecture works on a <b>request-response model</b>.<br>
<h3>Q) What happens when you open up your browser and type in your URL bar <br>
&nbsp;&nbsp;&nbsp;https://www.youtube.com/ and then press Enter?</h3><br>
<p>
Well, your browser, be it Google Chrome, or Safari, or Firefox, your browser is a client, and YouTube, for the sake of this example, is the server. <br>
Here, the client(browser) doesn't know actually what the server(YouTube) is.<br>
All that it knows, is that it can communicate with it. It can speak to it, it can request stuff from it.
But it doesn't actually know what the server represents. <br>
After typing the URL,  the browser doesn't even know how to talk with the server(Youtube).
<h3>1. Who to speak to ? </h3><br>
Behind the Scenes: our browser makes a <b>DNS query</b> to find out what the IP address of YouTube is, and only then it can really speak to YouTube. A DNS Query is a special request, that goes to a predetermined set of servers, and basically says <br>
<div align="center" style="margin-top:5px; margin-bottom: 5px">
"Hey, what's the IP Address of youtube.com?"</i>
</div>
An <b>IP Address</b> is just a unique identifier for a machine. All computers connected to the internet, have ways to find public IP Addresses, or at least, they have ways to discover routes to those addresses. And that means that, they can send data to IP Addresses. They can send packets of information, in the form of bytes, to IP Addresses. You can almost think of an IP Address as a mailbox, that some entity has granted to a machine. <br><br>
We can find ip address of any website using Terminal. Open the terminal, type 
<div align="center"><b>

```dig algoexpert.io```

</b></div>
This command allows us to do DNS Queries and then displays the answer in the terminal. This command gives the algoexpert.io's IP Address. And something very similar happens behind the scenes when in your browser, you type in algoexpert.io.<br><br>
Now the browser having the IP address, knows how to communicate directly with the server of AlgoExpert.
</p>
<br><br><br><br>
<div align="center">3</div>
<h3>2. How are we sending ?</h3>
Our browser sends an <b>HTTP request</b> to this IP Address. HTTP is a way to send information, that server can understand. So, when we say that a browser, or a client, sends an HTTP request to the AlgoExpert servers, basically it sends a bunch of bytes, or characters, that are gonna get packed into what we call packets, in some special format, and that's gonna be sent over to the AlgoExpert servers.<br><br><br>
<h3>3. How are we getting the response ?</h3>
And that request is also gonna contain the IP Address of the browser, or the computer, and that's gonna be called as the source of the request. And that's gonna be really important because when the server gets that request, it's gonna know what IP Address it should send a response to. So the AlgoExpert server will use that <b>source IP Address</b>, which is contained in the HTTP request. <br>
So the server of AlgoExpert now understands that when you go to algoexpert.io, you are trying to see the HTML of AlgoExpert and it returns in its response to the client.
And the browser receives the response and then renders the HTML on the page.<br><br>
<blockquote><b>Every website you browse, is built on the client-server architecture.</b></blockquote>
A very small percent of the business websites and applications use the peer-to-peer architecture, which is different from the client-server. <br><br><br>
<b>Note:- </b> A single machine or piece of software can be both a client and a server at the same time. For instance, a single machine could act as server for end users and as a client for a database.<br><br>
<h2> Ports </h2>
Servers are machines that are waiting to receive requests from clients. A server usually listens for requests on specific ports. Any machine that has a distinct IP Address, has 16000 ports that programs on the machine can listen to. <br>
Let's have some anaolgy: <br>
<div align="center"><b>
IP address - apartment<br>
ports - individual flats
</b></div><br>
So as a client, when you are communicating with a server, you actually have to specify the port that you wanna communicate on. <br>
When we're talking about the Client-Server Model here, it turns out that most clients actually know the port that they should use, depending on the protocol that they are trying to speak to the server with.<br>
HTTP protocol &nbsp;- port 80<br>
HTTPS protocol - port 443<br>
Secure Shell - port 22<br>
DNS lookup- port 53<br><br><br><br>
<div align="center">4</div>
<h2>Let's Visualize</h2>
You can simulate this client and server communication experience by opening two terminals using nc. <b>Netcat</b> (or nc) is a command-line utility that reads and writes data across network connections, using the TCP or UDP protocols.<br>
a. In one terminal type <code>nc -l 8081</code> (listen on 8081) <br>
b. In the other terminal type <code>nc 127.0.0.1 8081</code>.= Here, 127.0.0.1 is a special ip &nbsp;&nbsp;&nbsp;addresss that always points to your local machine. <br><br>
This simulates a connection between the two terminals. Anything typed in the second terminal will be seen in the first.<br><br>
<h1>Key Terms</h1>
<h2>CLIENT</h2>
A machine or process that requests data or service from a server.
<h2>SERVER</h2>
A machine or process that provides data or service from a client, usually by listening for incoming network calls.
<h2>CLIENT-SERVER MODEL</h2>
The paradigm by which modern systems are designed, which consists of clients requesting data or service from servers and servers providing data or service to clients.
<h2>IP ADDRESS</h2>
An address given to each machine connected to the public internet. IPV4 addresses consists of four numbers separated by dots: <b>a.b.c.d</b> where all four numbers are between 0 and 255. Special values include: <br>
- <b>127.0.0.1</b>: Your own local machine, also referred to as <b>localhost</b>.<br>
- <b>192.168.x.y</b>: Your private network. For instance your machine and all your machines on your private wifi network will usually have the 192.168 prefix.

<h2>DNS</h2>
Short for Domain Name System, it describes the entities and protocols involved in the translation from domain names to IP Addresses. Typically, machines make a DNS query to a well known entity which is responsible for returning the IP address (or multiple ones) of the requested domain name in the response.

<br><br><br><br><br><br><br>
<div align="center">5</div>
<h2>PORT</h2>
In order for multiple programs to listen for new network connections on the same machine without colliding, they pick a port to listen on. A port is an integer between 0 and 65,535 (216 ports total). <br>
Typically, ports 0-1023 are reserved for system ports (also called well-known ports) and shouldn't be used by user-level processes. Certain ports have pre-defined uses, and although you usually won't be required to have them memorized, they can sometimes come in handy. Below are some examples: <br>
- 22: Secure Shell <br>
- 53: DNS lookup <br>
- 80: HTTP <br>
- 443: HTTPS <br>

<h2>HTTP Protocol</h2>
The entire communication happens over the HTTP protocol. It is the protocol for data exchange over the World Wide Web. HTTP protocol is a request-response protocol that defines how information is transmitted across the web. <br>
It’s a stateless protocol, and every process over HTTP is executed independently and has no knowledge of previous processes.<br><br><br>
<b>Can the server initiate communication in a client server, request-response model ?</b><br>
No, its always the client<br><br><br>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<div align="center">6</div>
<h1 id="np">Network Protocols</h1>
<br><br>
Set of rules for communication between two machines.<br>
<h3>Q) What does a Network Protocol consists of?</h3>
A network protocol consists of the kinds of messages that are gonna be sent and received by machines, by clients and servers. The format of those messages, how they are structured, the order of those messages if they have an order, and whether or not they should be some sort of response to a message if there should be, what that response should look like, whether or not there should be rules around when messages can be sent, all of that stuff. <br><br>
There are a lot of network protocols out there but very few that are very popular and that are important to know about. We are gonna cover specifically IP, TCP, and HTTP. <br><br>
<h2>Internet Protocol (IP)</h2>
<blockquote><b>Modern Internet Effectively runs on IP</b></blockquote>
When a machine(client) tries to interact with other machine(server) and it sends data to that machine. Then that data is sent in the form of <b>IP packets</b>.<br>
Let's talk about IP packets.<br><br>

- Fundamental units of data that is sent from one machine to another.
- Building blocks of communication between machines over the internet.

IP Packets are actually made up of bytes. <br>They have 2 main sections: IP Header and the Data.<br>
<h3>Header</h3>
IP Header is the section of an IP Packet that is gonna be at the beginning of the packet. It contains all the <b>information about the packet</b> and that is stored in bytes. It contains the source IP Address, destination IP Address. <br>
If you have a single IP Packet, you know where that IP Packet is coming from and where it is going to. This is how information flows over the network, on the internet. This is how information knows to go from one machine to another. Because all these IP Packets have the source and destination IP Addresses of the machines that they are coming from and going to. <br><br>
The header also has other information like the total size of the packet, version of the Internet Protocol that this IP Packet is operating by. There are multiple versions of Internet Protocol and today, there are really 2 versions in practice. There's version 4 known as <b>IPV4</b>, this is really what most of the modern day internet uses, and then there's version 6, <b>IPV6</b> which is now being used more and more. Based on the IP version, the packet might look different. It might be structured a little differently, and a machine will know how it should interpret it based on that version.<br><br><br>
<div align="center">7</div>
The header is very small, anywhere between 20 and 60 bytes, and then the rest of the IP Packet is the data part of the IP Packet. <br><br><br>
<h3>Data</h3>
In the data portion of the IP Packet, the information that a machine is trying to send to another machine is gonna be stored.<br><br>
Now IP Packets are limited in size. They are only 2<sup>16</sup> bytes(64 KB). That's really nothing. If you are sending information over the network, you could imagine you might be sending an email, or a big file, or an image.
You are gonna be sending way more than 64 KB. <br><br>

If you are sending information over the network <br>
&nbsp;&nbsp;&nbsp;&nbsp; => that information is likely not gonna fit in one IP packet. <br>
&nbsp;&nbsp;&nbsp;&nbsp; => it will fit into <b>multiple IP packets</b><br><br>
This is where things get complicated. When you have multiple IP packets that are sent from one machine to another, if all you are using is the Internet Protocol, then <br>
1. You don't actually have a way of guaranteeing that these packets are actually gonna be received. It's very possible that some of the packets are gonna get lost, over the network. And if that's the case, you won't have sent all of the data that you were trying to send. <br>
2. You are also not guaranteeing the order in which the packets will be read or interpreted, and that's obviously not great because you want your packets to be ordered correctly such that your original data is sent in the correct order and in the correct structure that it's meant to be sent in. <br><br>

So Internet Protocol alone kind of falls apart here. <br>
&nbsp;And this is where TCP comes into play.
<h2>Transmission Control Protocol (TCP)</h2>
TCP is built on top of the Internet Protocol. <br><br>
It's really meant to solve the issues that exists in the IP : <br>
1. It's meant to send IP Packets in an <b>ordered way</b>, meaning that you are guaranteeing the order in which the IP Packets will be read by the destination machine. <br>
2. It's meant to send IP Packets in a <b>reliable way</b> meaning that you are guaranteed to get those packets actually received by the destination machine or at the very least you will know if some packets keep failing from getting received and in an error-free way. <br><br>

If some IP Packets get corrupted for whatever reason when they are being sent over the network, you will know and you will be able to resend those packets to make sure that they're received in an uncorrupted way. <br>
This is what TCP aims to solve in a nutshell. <br><br>
<div align="center">8</div>

An IP Packet has IP Header and the Data. In TCP, as TCP is built on top of IP, the IP Packet's data portion will have TCP Header and it contains the information about the ordering of the packets and some information about the packet.
<h3>Communication in TCP</h3>
Now, the core idea behind TCP is that when a machine wants to communicate with another machine over TCP, it is first going to create a TCP connection with the destination machine. And the way that's gonna happen is through what's known as a <b>handshake</b>.<br><br>
A Handshake is a special TCP interaction where one computer basically contacts the other by sending a packet or a few packets saying "Hey, I wanna connect with you."
The other computer responds and says, "Okay, we can connect, we can chat." And then the client or the machine that was trying to establish the connection re-responds again and says, "Okay, we're now connected, we've got an open connection." And this is known as a Handshake. <br><br>
And then once the connection is established, both machines can freely send data to one another but there are few things that might be worth knowing.<br>
- if one of the two machines doesn't send data in a given amount of period, the connection can be timed out.<br>
- if one of the machines wants to end the connection for whatever reason, it can do so by sending some sort of special message to let the other one know that "Hey, I'm about to end the connection." and then the TCP connection is done.<br><br>

To summarize, TCP is basically a more powerful, and more functional wrapper around IP. But still what it lacks is a really robust framework that developers, software engineers can use to really define meaningful and easy to use communication channels for clients and servers in the system. Because with TCP, all that you're really sending is arbitrary data that fits into these underlined IP packets. <br><br>
And this is where HTTP comes into play.<br>

<h2>Hypertext Transfer Protocol(HTTP)</h2>
HTTP is built on top of TCP. It introduces a higher level abstraction above TCP and of course IP.
And this abstraction is the <b>request-response paradigm</b>.<br><br>
So the HTTP protocol introduces this idea of having machines communicate with one another following this request-response paradigm where one machine sends request to another machine and that other machine returns a response to the first machine. And this request response paradigm with of course a set of accompanying rules makes it very easy for developers to create robust and easy to maintain systems. And so this is why most modern day systems rely on the HTTP protocol for communication.<br><br>
So with HTTP, we completely forget about IP packets, we forget about TCP. All that we deal with are HTTP requests and responses.<br><br><br><br><br><br>
<div align="center">9</div>
The best way to really understand or rather appreciate the power and the rigor that HTTP gives you, is to try to visualize what these request and responses look like. One can think of them as objects with important fields or properties that describe them. For example,<br>
Requests have fields such as url, port, method, headers, body etc.. <br>
Responses have fields such as status code, response body, headers etc.<br>
Headers are a collection of key value pairs that contain important metadata about the request or response.
<br><br><br>
If we go back to IP and TCP, those two protocols were more just for <b>transportation of data</b>. HTTP on the other hand introduces the opportunity to add a lot of <b>business logic</b> which is of course what you're gonna want if you're developing a large scale system or any kind of system to be honest. <br><br>
TP, TCP and HTTP are three very important protocols that basically any modern day system on the internet is gonna be relying on. IP and TCP are very very low level and you're typically not gonna be thinking about them much. HTTP is more relevant to you.<br><br><br><br><br>
<h1>Key Terms</h1>
<h2>IP</h2>
Stands for Internet Protocol. This network protocol outlines how almost all machine-to-machine communications should happen in the world. Other protocols like TCP, UDP and HTTP are built on top of IP.
<h2>TCP</h2>
Network protocol built on top of the Internet Protocol (IP). Allows for <b>ordered, reliable</b> data delivery between machines over the public internet by creating a <b>connection</b>.
TCP is usually implemented in the kernel, which exposes sockets to applications that they can use to stream data through an open connection.
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<div align="center">10</div>
<h2>HTTP</h2>
The HyperText Transfer Protocol is a very common network protocol implemented on top of TCP. Clients make HTTP requests, and servers respond with a response.<br><br>
Requests typically have the following schema:<br>
<blockquote>
host: string (example: algoexpert. io)<br>
port: integer (example: 80 or 443)<br>
method: string (example: GET, PUT, POST, DELETE, OPTIONS or PATCH)<br>
headers: pair list (example: "Content-Type" => "application/json")<br>
body: opaque sequence of bytes
</blockquote><br>
Responses typically have the following schema:<br>
<blockquote>
status code: integer (example: 200, 401) <br>
headers: pair list (example: "Content-Length" => 1238)<br>
body: opaque sequence of bytes
</blockquote><br>
<h2>IP Packet</h2>
Sometimes more broadly referred to as just a (network) packet, an IP packet is effectively the smallest unit used to describe data being sent over IP, aside from bytes. An IP packet consists of:<br>
- an IP header, which contains the source and destination IP addresses as well as other information related to the network<br>
- a payload, which is just the data being sent over the network

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<div align="center">11</div>
<h1 id="storage">Storage</h1>
If you think of any system that you might wanna design, you're probably gonna realize that, your system is gonna require some form of storage.<br>
This is where databases come into play.<br><br>
<h2>Database</h2>
A database is a thing that really serves two primary purposes:<br>
- To <b>store/write/set/record</b> data<br>
- To <b>retrieve/read/get/query</b> data<br><br>

Now one common misconception about databases is thinking that a database is this magical opaque box that lives somewhere in the ether. What a database really is, there are of course some exceptions, but what a database almost always is, is just a server. It is just like any other machine/computer.<br><br><br><br>
One very important concept in storage and in databases is <b>persistence</b>.<br>
A lot of people take for granted that if they store data in a database, that data will persist through any kind of issue that might occur in your system. They assume that if you store data in a database and then there's a power outage or a network issue or your database server crashes, once everything is booted back up, that the data will still be there.<br><br>
And while that assumption is often fair because a lot of databases do ensure that data stored in them is gonna persist through outages or issues, it isn't always correct. And this leads us to two fundamental things in storage: Disk and Memory <br><br>
<h3>Writing data to Disk</h3>
If you have a database server, and that database writes data to disk, that <b>data will persist</b> even if the database server goes down. Writing data to disk is basically what happens when you save a file on your computer. If you shut down your computer afterwards or if your computer crashes, that file that you saved is still gonna be there unless there's some catastrophic issue with your hardware or some other exceptional issue that data, that file, is still gonna be there.<br><br>
<h3>Writing data to Memory</h3>
In contrast, if your database writes data in memory, and this is what happens when for instance you've got your server code and you have maybe an array or a hash table declared in your server code and you store data in that array or in that hash table if that server goes down, if your database server goes down, and then gets booted back up, the array or the hash table in which you might have stored data is <b>no longer gonna have that data</b>.
That's what it essentially means to store data in memory.<br><br><br><br>
<div align="center">12</div>
<h3>Q) Why you'd ever want to use memory instead of disk ?</h3>
The simple reason is that reading data from memory or writing data in memory is much faster than reading data from disk or writing to disk.<br><br><br>
You can imagine if your database goes down, because your database is such a critical part of your system, then your entire system effectively goes down. <br>
And so then this brings us to the topic of distributed storage which adds further complexity as we have to maintain consistency throughout. <br><br><br>
There are hundreds of database offerings out there and each of them can give us certain properties or certain gurantees but will tradeoff others. <br><br><br>
<h1>Key Terms</h1>
<h2>DATABASE</h2>
Database is a program that either use disk or memory to do 2 core things: record data and query data. In general, they are themselves servers that are long lived and interact with the rest of your application through network calls, with protocols on top of TCP or even HTTP.
<h2>DISK</h2>
Disk Usually refers to either HDD (hard-disk drive) or SSD (solid-state drive). Data written to disk will persist through power failures and general machine crashes. Disk is also referred to as <b>non-volatile storage</b>.
<h2>MEMORY</h2>
Short for Random Access Memory (RAM). Data stored in memory will be lost when the process that has written that data dies.
<h2>PERSISTENT STORAGE</h2>
Usually refers to disk, but in general it is any form of storage that persists if the process in charge of managing it dies.
<br><br><br><br><br><br><br><br><br><br><br><br><br>
<div align="center">13</div>
<h1 id="landt">Latency And Throughput</h1>
Two most important measures of the performance of a system.<br><br>
<h2>Latency</h2>
It is basically<br>
- how long it takes for data to traverse a system.<br>
- how long does it take for data to get from one point in a system, to another point in a system.<br><br>

The latency of a network request is how long does it take for one request to go from a client to a server, and then back from the server to the client. The time that it's gonna take to read data from memory or disk is also gonna be referred to as latency. The most important aspect of latency is the fact that these <b>different things in systems have different latencies.</b><br><br><br>
Some examples of latencies of various operations : <br>
Reading 1 MB sequentially from memory RAM: &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;250 µs (0.25 ms) <br>
Reading 1 MB sequentially from SSD:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1,000 µs (1 ms) <br>
Transfer 1 MB over 1 GB/s Network: &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;10,000 µs (10 ms) <br>
Reading 1 MB sequentially from HDD:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 20,000 µs (20 ms)<br>
Sending a pakcet(<<1 MB) over network for round trip <br> between California and Netherlands: 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;150,000 µs (150 ms)<br><br>
> When you are gonna be designing systems, you're typically going to optimize those systems, by lowering the overall latencies of the systems.<br>

<div align="center"><b>low latency => faster data transfers</b></div>
<br>
<h2>Throughput</h2>
Throughput is how much work a machine can perform in a given period of time.<br><br>
When we talk about throughput, and we talk about this amount of work that a computer or machine can perform in a given amount of time, we're really referring to how much data can be transferred from one point in a system to another point in a system, in a given amount of time.<br>
And so typically, we measure this throughput, in gigabits per second, or kilobits per second, megabits per second.
<br><br><br>
Even though both are related to systems performance, they're not necessarily correlated.<br><br><br><br><br>
<div align="center">14</div>
<h1>Key Terms</h1>
<h2>LATENCY</h2>
The time it takes for a certain operation to complete in a system. Most often this measure is a time duration, like milliseconds or seconds.
<h2>THROUGHPUT</h2>
The number of operations that a system can handle properly per time unit. For instance the throughput of a server can often be measured in requests per second (RPS or QPS).
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<div align="center">15</div>
<h1 id="avail">Availability</h1>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<div align="center">
<h2><i>The content isn't available on this page<br>
Try checking on next page</i></h2>
</div>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<div align="center">16</div>
One way to think about it is how resistant a system is to failures.<br>
For instance, <br>
- what happens if a server in your system fails?<br>
- What happens if your database fails? <br>
- Is your system gonna completely go down or your system still gonna be operational?

And this is often described as a <b>system's fault tolerance</b>, how fault tolerant is a system ? <br><br><br>
Another way to think about availability is, as the <b>percentage of time in a given period of time</b>, like a month or a year, where the system is at least operational enough such that all of its primary functions are satisfied.<br><br><br>
Availability is a very important thing to think about when evaluating a system.<br> And in this day and age, especially, most systems almost have an implied guarantee of availability.<br><br>
<h2>How do you measure Availability?</h2>
We typically measure availability as the percentage of a system's uptime in a given year.
So, for instance, if a system is up and operational for half of an entire year, then you would say that that system has 50% availability.<br><br>
When we're dealing with availability, we're usually dealing very, very high percentages. Even an availability of 90% isn't really great. If you do the math, it means that your system is gonna be down about 35 or 36 days out of the year. So what that means is that in the industry, most services or most systems aim for really high availabilities and so we often end up measuring availability not exactly in percentages but rather in what we call nines.<br><br>
<h2>Nines</h2>
Nines are effectively percentages but they are specifically percentages with the number nine.
If you have a system that has 99% availability, meaning that it is up 99% of the time during a year.
Then, we say that your system has two nines of availability because literally the number nine appears two times in this percentage.<br><br>
If your system has 99.9% availability&nbsp; => three nines of availability. <br>
If your system has 99.99% availability => four nines of availability <br>
... <br>
and so on and so forth. And this is really the standard way that people talk about availability in the industry.
<br><br>
Five nines of availability is typically regarded as the <b>gold standard of availability</b>. If your system has five nines of availability, then we would really say that it is a highly available system (HA).<br><br><br><br>
<div align="center">17</div>
For certain systems, they don't have an implied guarantee of availability, they have an explicit guarantee of availability. Many service providers out there have SLAs.<br><br>
<h2>Service-Level Agreement (SLA)</h2>
SLA is an agreement between a service provider, basically the people who are behined the service or system that is being sold or provided, and the customers or end users of this service or of this system, an agreement on that system's availability amongst other things. <br><br>
SLO stands for <b>service-level objective</b>. SLO can be considered as components of SLA. In other words a service-level agreement is made up of service-level objectives. <br><br>
SLAs are taken very serious. And if the service provider fail to do so, they have to payback.<br><br><br>
When designing systems, you're gonna have to ask yourself: "What parts of my system are absolutely critical?" Well, not necessarily critical but are critical to the point that they require high availability. And what parts of my systems don't actually require high availability? What parts of my systems would be okay to fail? That's gonna be something that you'll have to think about.<br>
<b>Eg:-</b> For payments(stripe), we need high availability.<br><br><br>
<h2>How do you improve Availability?</h2>
Make sure that your system doesn't have <b>single points of failure</b>: Single places in your system that if they fail cause your entire system to fail. <br><br>
And how do you eliminate single points of failure? Answer is Redundancy. Redundancy is basically the act of duplicating or triplicating or multiplying even more certain parts of your system.<br>
Eg:- multiple servers, multiple load balancers etc...<br><br><br>
<h3>Passive Redundancy</h3>
When you have multiple components at a given layer in your system. And if at any point one of those components dies, nothing's really gonna happen.
The other components are basically gonna be able to continue running smoothly with the increased load.<br>
<b>Eg</b>:- Engines of an aeroplane<br><br>
<h3>Active Redundancy</h3>
When you have multiple machines that work together in such a way that only one or few of the machines are gonna be typically handling traffic or doing work. And if one of the ones that is handling traffic or doing work fails, the other machines are gonna somehow know that that other one failed and they're gonna take over.<br><br><br>
<div align="center">18</div>
<h1>Key Terms</h1>
<h2>AVAILABILITY</h2>
The odds of a particular server or service being up and running at any point in time, usually measured in percentages. A server that has 99% availability will be operational 99% of the time (this would be described as having two nines of availability).
<h2>HIGH AVAILABILITY</h2> 
Used to describe systems that have particularly high levels of availability, typically 5 nines or more; sometimes abbreviated "HA".
<h2>NINES</h2>
Typically refers to percentages of uptime. For example, 5 nines of availability means an uptime of 99.999% of the time. Below are the downtimes expected per year depending on those 9s: <br>
- 99% (two 9s): 87.7 hours <br>
- 99.9% (three 9s): 8.8 hours <br>
- 99.99%: 52.6 minutes <br>
- 99.999%: 5.3 minutes<br>

<h2>REDUNDANCY</h2>
The process of replicating parts of a system in an effort to make it more reliable.
<h2>SLA</h2>
Short for "service-level agreement", an SLA is a collection of guarantees given to a customer by a service provider. SLAs typically make guarantees on a system's availability, amongst other things. SLAs are made up of one or multiple SLOS.
<h2>SLO</h2> 
Short for "service-level objective", an SLO is a guarantee given to a customer by a service provider. SLOs typically make guarantees on a system's availability, amongst other things. SLOs constitute an SLA.
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<div align="center">19</div>
<h1 id="cache">Caching</h1>
Caching is used in a lot of algorithms. The reason is to typically avoid redoing the same operations, especially computationally complex operations that might take a lot of time, multiple times. So caching is used to improve the time complexity of the algorithms, to speed up the algorithms. <br><br><br>
And in the context of systems design, caching is actually pretty similar. To put it simply, caching is used to <b>speed up a system</b>. Caching is used to reduce or to improve the latency of a system.<br><br>
- Caching is going to be a way to design a system in such a way that, if we were originally gonna be using types of operations or data transfers that take a lot of time, like for example, network requests, we're gonna design a system in such a way that we don't have to do those network requests, and we can do different types of operations or different types of data transfers that are going to be faster. <br><br>
- Caching is gonna be storing data in a location that's different from the one where the data originally is, such that it's faster to access this data from this new location.<br><br><br><br>

<h2>Where can we use Caching ? </h2>
Caching can be used at different places in a system. For instance, you can cache at the client level. So that the client caches some data such that it no longer has to go to the server to retrieve it. Similarly, you could cache at the server level. Maybe you need the client to always interact with the server, but maybe the server doesn't always need to go to the database to retrieve data. Maybe it only needs to go to the database once and we can have some form of cache here at the server level.<br><br>
You could also have a cache in-between two components in a system. So maybe you could have a cache in-between a server and a database. In fact, you can even have caching at the hardware level. Now, perhaps this is less important in the context of Systems Design interviews, but it's still good to know about this. There is actually a lot of caching that happens at the hardware level in modern-day computers. For example, there's CPU caches, which are caches, as the name implies, that live at the CPU level, that basically make it faster to retrieve data from memory.<br><br>
It is good to know that caching can occur, or occurs by default, at many different levels of a system.<br>
<b>Note</b>:- Though caching is performed to speed up the slow operations, We can also use it incase of normal operations, not to spped them up individually but to avoid doing them multiple number of times because it might affect your system in other ways like increased load etc... <br><br><br><br>
<div align="center">20</div>
<h2>Editing cache data</h2>
<h3>Write Through Cache</h3>
A type of caching system where when you write a piece of data, your system will write that piece of data both in the cache and in the main source of truth (Database) at the same time, or rather in the same operation.<br> That way the <b>cache and the database are always in sync</b>.<br><br>
Now the down side to this is that you end up having to still go to the database.<br><br>
<h3>Write Back Cache</h3>
A type of caching system where when you write a piece of data, your system will write that piece of data in the cache only. <br>
So now your <b>cache will actually be out of sync with your database</b>.<br><br>
Behind the scenes, your system will asynchronously update the database with the values that are stored in the cache.
And this can be done in different ways. Maybe it's on certain intervals or on cache eviction.<br><br>
One of the downsides here is that if something ever happens to your cache and you lose the data in the cache, for instance, before the database has been updated asynchronously, then you're gonna lose data and that's really bad.<br><br><br>
<h2>Concept of Staleness</h2>
Say we have a bunch of servers and every server has a cache inside it. If for an operation, the cache of the first server got updated but the cache of the other servers are not updated yet, then the clients dealing with the other servers will be dealing with the stale versions of data. That would not be good. <br><br>
In this particular system (where staleness is considered), a solution would be to move our cache out of the servers and to put our cache, a single cache. Maybe this would be Redis. And all of the servers would hit the cache and we'd have this single source of truth for the caching mechanism.<br><br>
Example where staleness of data is considered: Comments on a YouTube video<br>
Example where staleness of data is not considered: Views on a YouTube video<br><br><br>
Lastly,
for immutable data, Caching is beautiful<br>
for mutable data, things gonna get trickier<br><br><br><br><br><br><br><br>
<div align="center">21</div>
<h2>Eviction policy in Caching</h2>
We do not have infinite space, so there is a limit for the amount of data stored in cache. To get rid of that data, we can use Least Recently Used policy (LRU), Least Frequently Used policy (LFU), Last in First out (LIFO), First in First out (FIFO), randomly etc..... depending on the usecase you are designing.<br><br><br><br>
<h1>Key Terms</h1>
<h2>CACHE</h2>
A piece of hardware or software that stores data, typically meant to retrieve that data faster than otherwise.
Caches are often used to store responses to network requests as well as results of computationally-long operations.
<h2>CACHE HIT</h2>
When requested data is found in a cache.
<h2>CACHE MISS</h2>
When requested data could have been found in a cache but isn't. This is typically used to refer to a negative consequence of a system failure or of a poor design choice. For example:
If a server goes down, our load balancer will have to forward requests to a new server, which will result in cache misses.
<h2>CACHE EVICTION POLICY</h2>
The policy by which values get evicted or removed from a cache. Popular cache eviction policies include LRU (least-recently used), FIFO (first in first out), and LFU (least-frequently used).
<h2>CONTENT DELIVERY NETWORK</h2>
A CDN is a third-party service that acts like a cache for your servers. Sometimes, web applications can be slow for users in a particular region if your servers are located only in another region. A CDN has servers all around the world, meaning that the latency to a CDN's servers will almost always be far better than the latency to your servers. A CDN's servers are often referred to as POPs (Points of Presence). Two of the most popular CDNs are Cloudflare and Google Cloud CDN.
<br><br><br><br><br><br><br><br><br><br><br><br>
<div align="center">22</div>
<h1 id="proxy">Proxies</h1>
When people use the term proxy, they often mean forward proxy.<br><br>
<h2>Forward Proxy</h2>
A forward proxy is a server that sits in between a client or a set of clients and another server or a set of other servers. But more specifically a forward proxy is a server that acts on behalf of the client or clients.<br><br>
In practice, what this means is that if a client wants to communicate with a server, assuming the forward proxy has been configured correctly by the client, when the client is gonna issue a request to the server, instead of going directly to the server, it's first gonna go to the forward proxy, which then is gonna forward the request to the server.<br><br>
It's almost like the client is saying,<br>
<div align="center"><b>"hey forward proxy, communicate with the server on my behalf please."</b></div><br>
 And when the server responds, it's gonna give its response to the forward proxy and then it will be forwarded to the client<br><br>
A forward proxy can serve as a way to <b>hide the identity of a client</b> that's requesting something from a server. Because the source IP address in the request going to the server is going to be the IP address of forward proxy and not that of the client. <br><br>
This is basically how <b>VPN</b>s work in a simplified way. It's a forward proxy. This means that a client might be able to access restricted servers that it's otherwise not supposed to access because the forward proxy might hide who this client really is. So this is how you might be able to access websites that are unavailable in your country, or that are restricted by your organization using a forward proxy.<br><br>
<div align="center">
<img src="https://www.researchgate.net/publication/327892898/figure/fig2/AS:675164312305665@1537983124995/Difference-between-Forward-Proxy-i-Reverse-Proxy-server-Source-Vivek-Srivastav-Proxy.jpg" height="230" width="500">
</div>
<br><br><br>
<div align="center">23</div>
In an interaction between a client and a server,<br>
&nbsp;&nbsp;&nbsp;forward proxies act on behalf of clients whereas <br>
&nbsp;&nbsp;&nbsp;reverse proxies act on behalf of a server. <br><br>
<h2>Reverse Proxy</h2>
If the client wants to send a request to the server, if the reverse proxy has been configured properly by the server or by the entity that owns the server, then when the client is gonna issue a request to the server, the request is actually gonna go to the reverse proxy. Then the reverse proxy is going to forward the request to the server then the server is gonna return a response to the reverse proxy and finally the reverse proxy is gonna return the response to the client.<br><br>
The key thing here is that client won't know that its request is going to a reverse proxy and thinks that it's interacting with the server. Even the DNS query will return the IP address of the reverse proxy. <br><br><br>
In forward proxy, it's the server that has no idea that the client and the forward proxy are kind of one and the same, whereas with the reverse proxy, it's the client that has no idea that the reverse proxy and the server are effectively one and the same. <br><br><br>
<h2>Uses of Reverse Proxy</h2>
Now reverse proxies are really useful because you can do a lot with them. <br>
- For instance, you might configure your reverse proxy such that it can filter out requests that you want to ignore.
Maybe for your system you don't want your servers to ever deal with certain kinds of requests so you can have your reverse proxy, kind of filter them out.<br>
- You can maybe have your reverse proxy take care of logging for your system. If you wanna log stuff, if you wanna gather metrics, maybe your reverse proxy can do that.<br>
- If you wanna cache stuff, maybe you wanna cache certain things like HTML pages. You might be able to do that at the reverse proxy layer and that way your server doesn't get bothered too much.<br>
- And one of the best use cases of a reverse proxy is using a reverse proxy as a <b>load balancer</b>. In a sentence, a load balancer is something like a server that is gonna effectively distribute the request load between a bunch of servers.

<br><br><br><br><br><br><br><br><br><br><br>
<div align="center">24</div>
<h1>Key Terms</h1>
<h2>FORWARD PROXY</h2>
A server that sits between a client and servers and acts on behalf of the client, typically used to mask he client's identity (IP Address). Note that forward proxies are often referred to as just proxies.
<h2>REVERSE PROXY</h2>
A server that sits between clients and servers and acts on behalf of the servers, typically used for logging, load balancing, or caching.
<h2>Nginx</h2>
Pronounced "engine X", not "N jinx". Njinx is a very popular webserver that's often used as a reverse proxy and load balancer. Learn more https://www.nginx.com/
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<br><br><br><br><br><br><br><br>
<div align="center">25</div>
<h1 id="lb">Load Balancers</h1>
Relentlessly distributing network requests across multiple servers, these digital traffic cops act as watchful guardians for your system, ensuring that it operates at peak performance day and night.<br><br>
<h2>Understanding Load balancers</h2>
Let's look at a simple use case. <br>
For example, let's assume there's a client and a server. The client issues requests and the server responds to the client. Imagine what would happen if our system became a little bit bigger? In other words, imagine instead of having one client issuing a request to our server, we had multiple clients, so maybe 2, 3 or 4 clients, all of them issuing requests to this server. And you could imagine that one of our clients might be issuing more than one request, one of our clients might be issuing a lot of requests. Our single server has limited resources. Our system has limited throughput. Our single server can only handle a limited amount of requests in a given amount of time.<br><br>
So what that means is that the more requests are being sent to the server, the more likely our server is to become overloaded, to receive more requests than it can handle. And that might lead to a failure in our system or maybe it'll just make our system very slow.<br><br>
<h3>So how do we handle this?</h3>
Well, the simple answer is, we scale our system.<br>
vertical scaling&nbsp;&nbsp; : increase the power of our single server <br>
horizontal scaling : add more servers to our system. <br><br>
And as you can imagine, horizontally scaling our system seems like a pretty obvious solution because if we have, let's say, 4 servers, we can now handle all of the requests from our clients in a balanced way. And assuming that our servers have the same resources, have the same power, our system will be able to handle four times the load that it was previously able to handle with only one server. But of course, this is assuming that all of our clients are going to be issuing requests to our servers in a balanced way. But this begs the question, <br><br>
<b>How did our clients know to issue their requests or rather to direct their requests to the servers in a balanced way?</b><br><br>
How come none of the clients issued their requests to the same server leading to the same problem that we had before?
<br>And this is of course where load balancers come into play.
<br><br><br><br><br><br><br>
<div align="center">26</div>
A load balancer is a server that sits in between a set of clients and a set of servers and that basically has the job of balancing workloads across the resources.<br><br>
What would happen in our example with the load balancer is that our clients would be issuing requests, that would go to the load balancer. And then the load balancers' job would be to redirect these requests in a balanced way or in some preconfigured way. So now, the traffic is evenly distributed across the servers.<br><br>
So load balancer is really useful because not only does it prevent resources like a single server or even multiple servers from getting overloaded, but it also makes your overall system have a better throughput.<br><br><br>
<h3>As a reverse proxy</h3>
And by the way, you can think of load balancers as types of reverse proxies most of the time because load balancers sit between clients and servers, and they typically act on behalf of these servers, which is exactly what a reverse proxy does.<br><br><br>
<h3>Where can we use load balancing ?</h3>
Load balancing can happen at a lot of different places in the system. For instance, you can have a load balancer between the clients and servers, another one between the servers and databases or when dealing with a website, you might even have load balancing at the DNS layer. Well, it turns out that there's something called DNS Round Robin, which is basically a type of load balancing that happens at the DNS layer, where a single domain name gets multiple IP addresses. And when a DNS query is made to get back IP address of that domain name, the multiple IP addresses that are associated with that domain name are going to be returned in a load balanced way.<br><br><br>
<h3>Types of load balancers</h3>
Software load balancers and Hardware load balancers. <br>
Hardware load balancers are literally physical machines that are dedicated to load balancing.
The main difference between hardware load balancers and software load balancers is that you can do more with software load balancers, you have more power over customization and scaling with software load balancers.
With hardware load balancers, you're limited to the hardware that you're given. And hardware is often expensive.<br><br>
We will look at software load balancers and the techniques that software load balancers use to distribute traffic to servers.<br><br>
<br><br><br><br><br><br><br>
<div align="center">27</div>
<h2>How to distribute the load ?</h2>
Does it follow a special algorithm? Does it do so randomly?<br>
Firstly, You have to make your load balancer such that when you add a new server or when you remove an old server, it registers /  deregisters itself with the load balancer correspondingly, so that the load balancer knows of its existence.<br><br>
There are a lot of different ways to select servers to send traffic.<br>
<h3>1. Pure random redirection</h3>
possible that one server would by chance get overloaded.<br><br>
<h3>2. Round Robin approach</h3>
A method that goes through all of your servers in one order. And so as you can imagine, that's pretty nice because you guarantee that you will be evenly distributing traffic across your servers. So this is a slightly preferred way.<br><br>
A slightly more complex type of Round Robin strategy is called a Weighted Round Robin, where you basically place weights on specific servers, meaning you would still follow the order of going to the first one first, then the second one, then the third one. But you might put a weight on, let's say, the second server, which would mean that when your load balancer is redirecting traffic to your second server, it's going to redirect a couple more requests, a little bit more traffic than it redirects to the other servers. And you could imagine that you might want to do that if, let's say, some of your servers are more powerful than the others.<br><br>
<h3>3. Based on performance or load</h3>
This strategy is a little bit more involved. Basically, your load balancer performs health checks on your servers to know how much traffic a server is handling at any given time, how long a server is taking to respond to traffic, how many resources a server is using, and based on that, it'll redirect traffic accordingly.<br><br>
<h3>4. Based on IP addresses</h3>
Basically, when your load balancer gets requests from clients, it's going to <b>hash</b> the IP address of the clients, and depending on the value of the hash, it will redirect the traffic accordingly.<br><br>
IP-based load balancing can be really useful if you've got for instance, caching going on in your servers.
You could imagine that within your system you're caching the results of requests in your servers, it would be very helpful to have requests from a specific client always be redirected to the server in which the response of that particular client's request has been cached.
And that can be accomplished through this IP-based load balancing.
IP-based load balancing can help you maximize cache hits.<br><br><br><br><br><br><br>
<div align="center">28</div>
<h3>5. Based on path</h3>
With this strategy, a load balancer basically distributes requests to servers according to the path of the requests. <br>
<b>Eg</b>:- download functionality to a server or a set of servers,<br>
handling payments to a server or a set of servers etc..<br><br><br><br>
And you're likely to even have multiple load balancers at the same part of a system because as you might be wondering, <br>
<b>what happens if a load balancer starts to get overloaded? </b><br>
Well, this is where you could have a second load balancer or even a third load balancer.
These load balancers could communicate between each other, and depending on that, reroute traffic accordingly. <br><br>
Ultimately, load balancers are very simple, but they're extremely important.<br><br><br><br>
<h1>Key Terms</h1>
<h2>LOAD BALANCER</h2>
A type of reverse proxy that distributes traffic across servers. Load balancers can be found in many parts of a system, from the DNS layer all the way to the database layer.
<h2>SERVER-SELECTION STRATEGY</h2>
How a load balancer chooses servers when distributing traffic amongst multiple servers. Commonly used strategies include round-robin, random selection, performance-based selection (choosing the server with the best performance metrics, like the fastest response time or the least amount of traffic), and IP-based routing.
<h2>HOT SPOT</h2>
When distributing a workload across a set of servers, that workload might be spread unevenly. This can happen if your sharding key or your hashing function are suboptimal, or if your workload is naturally skewed: some servers will receive a lot more traffic than others, thus creating a "hot spot".<br><br><br><br><br><br><br><br><br><br>
<br><br><br><div align="center">29</div>
