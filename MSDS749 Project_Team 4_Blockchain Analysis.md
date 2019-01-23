# Blockchain Analysis (April 2019)

    Yumei Bennett, Graduate Student, Southern Methodist University, Daniel Byrne, Graduate Student, Southern Methodist University, Benjamin Wilke, Graduate Student, Southern Methodist University, Brian Coari, Graduate Student, Southern Methodist University

*Abstract— Blockchain technology is at the heart of bitcoin and is increasingly being developed for use in a broad range of financial applications.The goal of this project is to provide a survey and tutorial on Blockchain technology. The project and writeup will include an evaluation of an experimental Blockchain database.*

*Index Terms— Computer network management, Cooperative communication, Cryptographic protocols, Data transfer, Encryption, Distributed databases, Document handling, Fault tolerant control, Identity management systems, Information exchange, Internet, Network function virtualization, Network security, Peer-to-peer computing*

## INTRODUCTION
THIS paper will explore the distributed ledger technology known as Blockchain. In this paper we will cover what Blockchain is, the theories and technologies behind Blockchain, its strengths and shortcomings, as well as its current and possible future uses. We will explain the different types of Blockchains (public, private, and Federated), and the pros and cons of each. We will end the paper with a sample demonstration of a simple Blockchain we created using BigChain, using visuals to walk through the process step-by-step so the reader leaves with a thorough understanding of how Blockchain works.
	
In this paper we will explain that Blockchain is, at its heart, simply a system that tracks a history of events called a [digital ledger][1]. We will define terms such as Blocks, the Blockchain Distributed Database, Block Time, and the Blockchain Community. We will examine, in detail, how every event knows a unique identifier of the event that came before it, and when the event is approved by the Blockchain Community the event is given a timestamp and added to its chain. When an event is added to a chain, ever user that is part of the Blockchain Community adds that event to their copy of that chain simultaneously, which creates the [Blockchain Distributed Database][2]. This helps prevent tampering with the events in a chain, since an attacker would need to edit every chain from every user in the Blockchain Community for a change to be accepted, which means the attacker would need access to the private databases of everyone in the Blockchain Community. By this use of the Blockchain Distributed Database, Blockchain ensures trust in the history of its transactions and makes it an attractive fit for any process that values a [trusted history][1].

We will also explore the different types of Blockchains: Public, Private, and Federated. We will explain how public blockchains allow anyone to submit transactions to the blockchain and become part of the Blockchain community, how private blockchains restrict access to submit and verify transactions, and how Federated Blockchain is like a Private Blockchain but allows many organizations to have nodes on the network. We will give some examples and pros and cons of each of these [blockchain types][3].

At the end of this paper the goal is for the reader to not only have a thorough understanding of why Blockchain exists and what solutions it can provide, but also to be able to join an existing Blockchain instance or to start his or her own Blockchain with some confidence that it can provide the trust missing from so many independent and private transactions.

## A Brief History of Blockchain
Blockchain technology represents the next step in the peer-to-peer
economy.14 By combining peer-to-peer networks, cryptographic algorithms, distributed data storage, and a decentralized consensus mechanisms,15 it provides a way for people to agree on a particular state of affairs and record that agreement in a secure and verifiable manner.



REFERENCES
[1]:	https://blockgeeks.com/guides/what-is-blockchain-technology/ "Judd Bagley (2018 ,  Sep . ).  What is Blockchain Technology? A Step-by-Step Guide For Beginners. Blockgeeks." 
[2]:	https://medium.com/blockchain-review/how-does-the-blockchain-work-for-dummies-explained-simply-9f94d386e093 "Collin Thompson (2016 Oct.). How does the Blockchain Work? (Part 1). The Blockchain Review." 
[3]:	https://blockchainhub.net/blockchains-and-distributed-ledger-technologies-in-general/ "Collin Thompson (2016 Oct.). Blockchains & Distributed Ledger Technologies. BlockchainHub."

