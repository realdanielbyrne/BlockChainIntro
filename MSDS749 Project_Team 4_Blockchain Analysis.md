# Blockchain Analysis (April 2019)

    Yumei Bennett, Graduate Student, Southern Methodist University, Daniel Byrne, Graduate Student, Southern Methodist University, Benjamin Wilke, Graduate Student, Southern Methodist University, Brian Coari, Graduate Student, Southern Methodist University

*Abstract— Blockchain technology is at the heart of bitcoin and is increasingly being developed for use in a broad range of financial applications.The goal of this project is to provide a primer on Blockchain technology. This project and writeup will include an evaluation of an experimental Blockchain database.*

*Index Terms— Computer network management, Cooperative communication, Cryptographic protocols, Data transfer, Encryption, Distributed databases, Document handling, Fault tolerant control, Identity management systems, Information exchange, Internet, Network function virtualization, Network security, Peer-to-peer computing*

## INTRODUCTION
THIS paper will explore the distributed ledger technology known as Blockchain. In this paper we will cover what Blockchain is, the theories and technologies behind Blockchain, its strengths and shortcomings, as well as its current and possible future uses. We will explain the different types of Blockchains (public, private, and Federated), and the pros and cons of each. We will end the paper with a sample demonstration of a simple Blockchain we created using BigChain, using visuals to walk through the process step-by-step so the reader leaves with a thorough understanding of how Blockchain works.
	
In this paper we will explain that Blockchain is, at its heart, simply a system that tracks a history of events called a [digital ledger][1]. We will define terms such as Blocks, the Blockchain Distributed Database, Block Time, and the Blockchain Community. We will examine, in detail, how every event knows a unique identifier of the event that came before it, and when the event is approved by the Blockchain Community the event is given a timestamp and added to its chain. When an event is added to a chain, ever user that is part of the Blockchain Community adds that event to their copy of that chain simultaneously, which creates the [Blockchain Distributed Database][2]. This helps prevent tampering with the events in a chain, since an attacker would need to edit every chain from every user in the Blockchain Community for a change to be accepted, which means the attacker would need access to the private databases of everyone in the Blockchain Community. By this use of the Blockchain Distributed Database, Blockchain ensures trust in the history of its transactions and makes it an attractive fit for any process that values a [trusted history][1].

We will also explore the different types of Blockchains: Public, Private, and Federated. We will explain how public blockchains allow anyone to submit transactions to the blockchain and become part of the Blockchain community, how private blockchains restrict access to submit and verify transactions, and how Federated Blockchain is like a Private Blockchain but allows many organizations to have nodes on the network. We will give some examples and pros and cons of each of these [blockchain types][3].

At the end of this paper the goal is for the reader to not only have a thorough understanding of why Blockchain exists and what solutions it can provide, but also to be able to join an existing Blockchain instance or to start his or her own Blockchain with some confidence that it can provide the trust missing from so many independent and private transactions.

## A Brief History of Blockchain

### Early Cryptogrpahy
Until about the 1970s, cryptography was mainly the purview of state actors. However, in the 70s, two publications brought cryptography into the public eye the US Government's DES, the Data Encryption Standard, and Whitfield Diffie & Martin Hellmanand's publication on public key cryptography. [10]

### DES
The Data Encryption Standard is a symmetric-key, block cipher algorithm for the electronic data encryption first developed at IBM, and then submitted as a candidate in a invitational study to the National Bureau of Standards, now the national Institute of Standards and Technology, following the agency's invitation to help define a government wide standard encryption algorithm for the protection of sensitive, but unclassified electronic government data.  The inital IBM submission was modified, with input from the National Security agency, and through testing at IBM and NBS from the original.  

Symmetric-key or shared-key algorithms like DES are cryptographic algorithms the use the same or very midly transformed keys for both encryption decryption of data. The keys enable the possibility of a secure communication link between 2 or more parties. The requirement of this type of secure channel is that all parties to the communication need to know the secret keys.  This fact represents the main drawback to symetric key algorithms as the number of communicating parties increases it becomes exceedinlgy more complex to engineer a secure means of transferring the secret keys before the encrypted communication using the keys can begin.

Block ciphers are cyrptographic algorithms which deterministically transform a fixed length groups of bits called a block. In a typical block cipher implementation data is split up into equal size blocks which are then passed through into a transformation block along with a key which then ouputs the transformed block.  However, since each block is deterministic and unwavering, block ciphers are susceptible to an exploit called differential cryptanalysis
in which output blocks are scanned for evidence of non random behavior caused by some repeating value on the input, and then use that information to reverse engineer the encryption keys.  

Substitution blocks are a cryptographic algorithms in which an input set of bits n are transformed into an output set of bits m, and where n and m are not neccessiarily alike.  DES incorporated the first widely used implementation of substitution blocks in its 6x4 s-blocks in which 6 input bits were transformed to 4 output bits. 

During the public comment period parts of the proposed standard were deemed classified, and thus could not be vetted by researchers in the field. Due to the partially classified nature of the publication, the involvement of the NSA, and the introduction of heretofore unknown feature in the design called S-boxes, the initial specificaion was immediately met with wide skepticism in the academic realm.  Whitefield Diffle and Martin Hellman, prominent cryptography researchers at Standford University, panned the standard in an [Exhaustive Cryptanalysis of the NBS Data Encryption Standard][11]. Primarily their concern was that the 56bit key proposed by the standard was too short to be secure.  There was also public skepticism that the classified, heretofore unknown to the cryptographic community, S-boxes, now know as substitution boxes, in the design represented some sort of backdoor introduced by the NSA to allow it to decrypt secure communications.  It wasn't until years later when S-boxes were rediscovered, that it was determined that the inclusion of S-boxes in the DES standard made it actually more secure against differential cryptanalysis.  However, the NSA did push for a reduction of the key size from the originally proposed 64bits to 48bits.  IBM eventually agreed to a compromised 56bit key, thus making it possible, for state actors and organizations with deep pockets to build a computer to crack DES encryption through brute force methods, even in the late 1970s.  In Diffie and Hellman's public shaming of DES they made that point in the openning introduction.[11]

### Public Key Cryptography
Blockchain technology grew out of the tenenats of a group of high tech privacy enthusiasts calling themselves Cypherpunks. The term cypherpunk is a compound word combining root words *cypher*, a coded message, and *punk*, in this instance referencing a member of a rebellious counterculture group.  The Cypherpunk movement traces its roots to the early days of public key cryptogography and specifically to the work of cryptographer David Chaum.  David Chaum laid the technical groundwork for the Cypherpunk movement with his landmark papers inventing the [Blind Signature][8] in which the content of a message is encrypted before it is signed, and transaction systems without a central authority in a paper entitled ["Security without identification: transaction systems to make big brother obsolete."][7]  

The Cypherpunk group started out in the as in informal meetup betwen like minded individuals foundeded by Eric Hughes, Tim May, and John Gilmore.  These three together with 20 of their friends began meeting regularly in the offices of John Gilmore's company, Cygnus, a stalwort of the burgenoning open source community,in the early 1990s.  There they discussed 

The group started the Cypherpunk mailing list shortly after to broaden its appeal and to attract like minded individuals from around the world.   It its heyday in the 90s, there was over a 1000 subscribers, and boasted a high (at the time) of 30 messages or more a day.  

In 1998, the Electronic Frontier Foundation built a $200,000 machine that finds a Data Encryption Standard key in a few days; details are in Cracking DES [13]. See our DES article for background.

The project leader was John Gilmore, and the goal of the project was to demonstrate beyond question that DES was insecure. As many cypherpunks saw it, this was necessary because the US government had been telling deliberate lies about the security of DES for some time.


REFERENCES
[1]:	https://blockgeeks.com/guides/what-is-blockchain-technology/ "Judd Bagley (2018, Sep).  What is Blockchain Technology? A Step-by-Step Guide For Beginners. Blockgeeks." 
[2]:    https://medium.com/blockchain-review/how-does-the-blockchain-work-for-dummies-explained-simply-9f94d386e093 "Collin Thompson (2016 Oct.). How does the Blockchain Work? (Part 1). The Blockchain Review." 
[3]:	https://blockchainhub.net/blockchains-and-distributed-ledger-technologies-in-general/ "Collin Thompson (2016 Oct.). Blockchains & Distributed Ledger Technologies. BlockchainHub."
[4]:    https://bitcoin.org/bitcoin.pdf "Nakamoto, Satoshi (31 October 2008). 'Bitcoin: A Peer-to-Peer Electronic Cash System (PDF).' Retrieved 20 December 2012."
[5]:    https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2580664 "Decentralized Blockchain Technology and the Rise of Lex Cryptographia"
[6]:    https://www.activism.net/cypherpunk/manifesto.html "A Cypherpunk's Manifesto"
[7]:    https://dl.acm.org/citation.cfm?doid=4372.4373 "Security without identification: transaction systems to make big brother obsolete."
[8]:    http://www.hit.bme.hu/~buttyan/courses/BMEVIHIM219/2009/Chaum.BlindSigForPayment.1982.PDF "Blind Signatures for Untraceable Payments"
[9]:    http://en.citizendium.org/wiki/Cypherpunk/Citable_Version "Cypherpunk/Citable Version"
[10]:   https://www.cs.jhu.edu/~rubin/courses/sp03/papers/diffie.hellman.pdf "Diffie, Whitfield & Martin Hellman (Nov. 1976), "New Directions in Cryptography", IEEE Transactions on Information Theory IT-22: 644-654"
[11]:   https://web.archive.org/web/20140226205104/http://origin-www.computer.org/csdl/mags/co/1977/06/01646525.pdf "Exhaustive Cryptanalysis of the NBS Data Encryption Standard"
