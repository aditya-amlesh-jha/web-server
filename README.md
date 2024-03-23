# web-server

# website
https://www.example.com/
protocol:ip_address:port:api


# Create a go project
go mod init project-name


# Networking Layer
1.Application layer: applications that serves the data that user wants, DNS for websites lookup, FTP for file transer, HTTP for website delivery, SMTP for mail
2. Transport layer: responsible for end to end communication between devices across the network. TCP is implemented here which contains send buffer, recieve buffer
3. Internet Layer: handle traffic routing and controlling flow of traffic. It deals with routing of packages across multiple interconnected devices. IP is used for identiying devices on the network. also responsible for fragmentation and reassembly of data packets when dealing with different network technology
4. Access/Link Layer: components of a device that make networking possible(ethernet cable, network interface card, wifi), makes possible physical transmission of data between nodes on same network segment


# How server works
Client sends request in the form of:
"GET / HTTP/1.0
Host: hostname.com"

# TCP Layer
TCP Layer implements IP layer which has 3 components:
1. Sender's address
2. Receiver's address
3. message data

TCP implements does not implement packet delivery of data which has 3 problems:
1. message data may exceed capacity of single packet
2. the package may get lost
3. out of order packets

TCP solves delivery problem of packets by implementing:
1. ordered delivery of data (byte streams) instead of packets

How TCP connection works:
1. Initially server waits for client at IP+port which is known as bind and listen. Then client connects to it through 3 step Handshake(SYN, SYN-ACK, ACK)
2. Once connection is established, messages are transferred(can be bidirectional/full duplex/socket)
3. A device in connection sends no data will be sent through FIN flag, other side ACKs the FIN and connection is terminated

