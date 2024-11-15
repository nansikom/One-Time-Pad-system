## One-Time Pad Encryption and Decryption Programs
## Overview
This assignment involves creating a suite of five programs that perform encryption and decryption using a one-time pad-like system. The programs implement inter-process communication (IPC) via network sockets and combine multiprocessing with client-server communication. Additionally, a standalone utility for key generation is included. These programs utilize Unix features such as input/output redirection and job control, emphasizing modular design and networking concepts.

## Learning Objectives
Understand IPC Mechanisms: Compare and use different IPC facilities.
Client-Server Communication: Design and implement networked applications using sockets.
Encryption Techniques: Apply one-time pad encryption/decryption using modular arithmetic.
Network Programming: Utilize the Unix socket API for secure communication.
Error Handling: Build robust programs capable of handling and reporting errors.
Program Descriptions
1. enc_server
A daemon program that encrypts plaintext using a key.
Accepts up to 5 simultaneous connections.
Communicates with enc_client over a specified port.
Uses sockets for data exchange.
Rejects unauthorized connections and invalid inputs.
Usage:

bash
Copy code
enc_server <listening_port> &
2. enc_client
Connects to enc_server to request encryption of plaintext.
Reads plaintext and key from input files and sends them to the server.
Outputs ciphertext to stdout.
Usage:

bash
Copy code
enc_client <plaintext_file> <key_file> <port> > <output_file>
3. dec_server
A server similar to enc_server, but for decryption.
Communicates only with dec_client.
Returns plaintext by decrypting ciphertext with a key.
Usage:

bash
Copy code
dec_server <listening_port> &
4. dec_client
Connects to dec_server to request decryption of ciphertext.
Reads ciphertext and key from input files and sends them to the server.
Outputs plaintext to stdout.
Usage:

bash
Copy code
dec_client <ciphertext_file> <key_file> <port> > <output_file>
5. keygen
Generates a random key of specified length consisting of the 27 allowed characters (A-Z, space).
Outputs the key to stdout.
Usage:

bash
Copy code
keygen <keylength> > <key_file>
References
Wikipedia: One-Time Pads
Note:This assignment was hosted by Oregon State University
