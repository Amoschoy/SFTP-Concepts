# SFTP-Concepts

Examples of Systems
1. Source System
2. Active Transfer Server
3. Consumer System

Certificates
- Public and Private key (Source System)
- Public and Private key (Active Transfer Server)
- Public and Private key (Consumer System)


What is SFTP?

SFTP, or Secure File Transfer Protocol, is a secure file transfer protocol that uses secure shell encryption to provide a high level of security for sending and receiving file transfers. SFTP is similar to FTPS in that it uses AES and other algorithms to secure data as it travels between different systems.


How does SFTP work?

Using Active transfer SFTP Public Key Authentication as an example.

The whole file transfer process consists of three locations: source system, active transfer(AT) and consumer system.

(1) AT will want to access source system to PULL a file from a folder in source which (2) AT will then process (filtering rules) the file and (3) lastly the consumer system will access AT to pull the file from virtual folder in AT.

From (1) to (2), the AT (SFTP client) is the initiator as it wants to PULL file from source system (SFTP server) hence it will send its public key to be stored in source system.

Whenever AT wants to get access to source system, the AT's private key will generate a digital signature that the source system, through the AT public key stored there, can match with the user's account.

cid:65f08800-e0c1-4545-a5c1-54b0a900a3e5![image](https://github.com/Amoschoy/SFTP-Concepts/assets/91897502/0ed8a5e1-8910-4455-a84d-57d3585c6ff1)



From (2) to (3), consumer system (SFTP client) will be the initiator as it wants to PULL the processed file from AT (SFTP server)

Hence, consumer system will send its public key to be stored inside AT server.

Similarly, whenever consumer system wants to get access to AT SFTP server, the consumer system's private key will generate a digital signature that the AT server, through the consumer system's public key stored there, can match with the user's account.
