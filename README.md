## Implementation of OSI model

### Layers
Layers is organized as separate functions for each layer of the OSI model. A user inputs a message and the program passes it to the top layer (Application Layer), which then passes it down layer by layer to the bottom layer (Physical Layer). Each function performs the layer's duties and prints the progress along the way. Some notable layers are the Transport and Network Layers, which add a port and IP to the message's headers, and the Data Link Layer, which utilizes a find and replace to implement Bit Stuffing and converts the message into bytes using ascii-to-bytes with padding to ensure there are always eight 1s or 0s per letter.
All function included:

application_layer
presentation_layer
session_layer
transport_layer
network_layer
datalink_layer
physical_layer


### Bit Stream Encoding

Bit stream encoding is necessary for error detecting. Information generated by an application is encoded so that information going into the communication channel follows a specific pattern. The checksum algorithm a common error detecting code. The 16-bit Internet checksum is used on all Internet packets as part of the IP protocol.
Checksum refers to a group of check bits associated with a message. The checksum is computed as a function of the transmitted message. The computed checksum is appended to the original message. An error may be detected by summing the entire received codeword, which consists of both the message bits and the checksum. If the result comes out to a zero, then no error is detected. 
We implemented the checksum algorithm with a python script. The main program in the script runs the following code:

Once the checksum is computed, the verifier(message, checkSum) message checks to see if the message is error free by computing 
result  = (sum + bL) % moduloValue

If the result is 0, then no error occurred. Otherwise, an error is detected. 


### Undirected Graph Network

This program implements a undirected graph in python to act as network. There are six nodes in the current implementation with each connection being and edge with an associated delay. Nodes are labeled A, B, C, D, E, F and each delay for each node connection was abitrarily chosen. In the main function of the python program the graph is instantiated and a undirected graph is created (see below). Dijkstra's algorithm was created and called in main using 


### Server and Client

When the server is run, a socket is created and the server listens for text to enter the buffer. When the client is run, it connects to the same socket. As seen in the program output below, there are several stages of the program labeled alphabetically. 

* A: The client sends HELLO / the server listens for HELLO.
* B: The server sends an ACK / the client listens for an ACK.
* C: The client sends a requested filename / the server listens for a filename.
* D: The server sends the file (from the source folder) to the client / the client receives the file and saves it (in the destination folder).
* E: The client sends an ACK / the server listens for an ACK. Both programs terminate.

The programs consider both UDP and TCP.
