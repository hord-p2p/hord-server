# HORD

> NOTE: this readme does not cover the technical details. Look at implementation guide [here](implementation.md).

a p2p file/data sharing project, HORD consists of 2 main components for now, a client and a server.

client can generates public and private key. public key is used to identify the client, private key is used to sign file chunks.

a client can create a network. another client can join the network by connecting to same server and sharing the public key to network host client.

a network is a group of clients connected to same server. server can host multiple networks.

much like torrent but safer.

server only connects clients. file chunking, encryption and distribution is done by the clients


files are chucked and an encrypted chunk map is created and stored on the server. client decrpts chunk map and locates chunks on other clients through chunk map.

whole network shares a secret key used to encrypt chunk map and chunks.


Clients will measure RTT (round trip time) and throughput to peers and pull chunks in parallel from several of them. Use rarest-first ordering, like BitTorrent, so chunks spread across the network quickly.


trust network and zero-knowledge keeps it safe
