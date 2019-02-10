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

The Data Encryption Standard is a symmetric-key, block cipher algorithm for the electronic data encryption first developed at IBM, and then submitted as a candidate in a invitational study to the National Bureau of Standards, now the national Institute of Standards and Technology, following the agency's invitation to help define a government wide standard encryption algorithm for the protection of sensitive, but unclassified electronic government data. IBM's submission was modified to use S-blocks and to decrease the number of bits used for the key as suggested by the National Security Agency before final ratification of the standard.  The final design was a symmertric key, 56-bit, block encryption alogrithm using S-block, or substitution blocks.

Symmetric-key or shared-key algorithms like DES are cryptographic algorithms the use the same or very midly transformed keys for both encryption decryption of data. The keys enable the possibility of a secure communication link between 2 or more parties. The requirement of this type of secure channel is that all parties to the communication need to know the secret keys.  This fact represents the main drawback to symetric key algorithms as the number of communicating parties increases it becomes exceedinlgy more complex to engineer a secure means of transferring the secret keys before the encrypted communication using the keys can begin.

Block ciphers, like DES, are cyrptographic algorithms which deterministically encrypt fixed length groups of bits. In a typical block cipher implementation data is split up into equal size blocks which are then passed through into a transformation block along with a key which then ouputs the transformed block.  However, since each block is deterministic and unwavering, block ciphers are susceptible to an exploit called differential cryptanalysis in which output blocks are scanned for evidence of non random behavior caused by some repeating value on the input, and that information is used to reverse engineer the encryption keys.  

Substitution blocks, at the time a new feature in cryptogrraphy are a cryptographic algorithm in which an input matric of n bits are transformed into an output matrix of bits, and where n and m are not neccessiarily alike.  DES incorporated the first widely used implementation of substitution blocks in its 6x4 s-blocks in which 6 input bits were transformed to 4 output bits.

During the public comment period, parts of the proposed standard were deemed classified, and thus could not be vetted by researchers in the field. Due to the partially classified nature of the publication, the involvement of the NSA, and the introduction of heretofore unknown feature in the design called S-boxes, the initial specificaion was immediately met with wide skepticism in the academic realm.  Whitefield Diffle and Martin Hellman, prominent cryptography researchers at Standford University, panned the standard in an [Exhaustive Cryptanalysis of the NBS Data Encryption Standard][11]. Primarily their concern was that the 56bit key proposed by the standard was too short to be secure.  There was also public skepticism that the classified implementation of the S-boxes, now know as substitution boxes, in the design represented some sort of backdoor introduced by the NSA to allow it to decrypt secure communications.  

It wasn't until years later when S-boxes were rediscovered, that it was determined that the inclusion of S-boxes in the DES standard made it actually more secure against differential cryptanalysis.  However, the NSA did push for a reduction of the key size from the originally proposed 64bits to 48bits.  IBM and the NSA eventually setteled on a compromised 56bit key, thus making it possible according to Dilfe and Hellman, for state actors and organizations with deep pockets to build a computer to crack DES encryption through brute force..  In Diffie and Hellman's public shaming of DES they made that point in their openning introduction.[11]  

### Public Key Cryptography

Dilfe and Hellman went on to advocate for public key encryption and to patent the first public key encryption algorithm, the Dilfe Hellman Key exchange protocol.  Public-key cryptography is an algorithm that uses a pair of prime number keys, one public and one private to produce an encryption based upon the product of these keys called a "one-way function".  A one-way function is a function that is computationally simple, for a computer, to compute on every input, but hard to factor without priori knowledge of the prime factors.

The public key can we widley diseminated without fear that the encrypted data can be compromised. The security of this cryptographic system is determined by the sheer complexity and time it would take to factor the the product of the two very large prime keys with current technologly.

### Cipher Punks

Blockchain technology grew out of the tenenats of a group of high tech privacy enthusiasts calling themselves Cypherpunks. The term cypherpunk is a compound word combining root words *cypher* or  *cipher*, a coded message, and *punk*, in this instance referencing a member of a rebellious counterculture group advocating widespread use of cryptography as a means to social and political change.

The Cypherpunk movement traces its roots to the early days of public key cryptogography.  With the initial academic uproar surrounding the distrust of the NSA's involvement in the manipulation of DES, and the secrecy in which the implementation of the algorithm was srounded, there began the seeds of disent and the onus for the beginnings of the cypherpunk movement.  The eerily precient early focus of the small mostly online group was on discussing questions about privacy, government monitoring, and corporate control of information, all issues which are in national converation today.

The Cypherpunk group started out in the as in informal meetup betwen tech minded individuals with scofflaw tendencies foundeded by Eric Hughes, Tim May, and John Gilmore.  These three together with 20 of their friends began meeting regularly in the offices of John Gilmore's company, Cygnus, a stalwort of the burgenoning open source community, in the early 1990s.  

Their meetup shortly after morphed into a mailing list to broaden its appeal and to attract like minded individuals from around the world.  Their primary concern was that of governments and large powerful corporte entites capturing information, as John Gilmore said it in a speech at the first ACM conference on Computers in March 1991,

"In most of Europe, phone companies don't record the phone numbers when you call, and they don't show up on your bill. They only tick off the charges on a meter. Now, I was told that this is partly because the Nazis used the call records that they used to have, to track and identify the opposition after taking over those countries in World War II. They don't keep those records any more."

The mailing list's topics and  tenor favored privacy in communications, self revalation, financial privacy, anonimity, and pseudonyms.  It also derided and actively opposed givernment data collection, forced self revalation, and censorship. It is notable that an early and very active, member of the Cypherpunk mailing list was Julian Assange of Wikileaks.

Privacy in communication was a primary concern of the movement, but equally importatnt to the movement and to the discussion on teh mailing list were discussion around financial privacy, as Eric Hughes, one of the founderes of the movement, puts it in the Cypherpunk Manifesto,

"When I purchase a magazine at a store and hand cash to the clerk, there is no need to know who I am. When I ask my electronic mail provider to send and receive messages, my provider need not know to whom I am speaking or what I am saying or what others are saying to me; my provider only need know how to get the message there and how much I owe them in fees. When my identity is revealed by the underlying mechanism of the transaction, I have no privacy. I cannot here selectively reveal myself; I must always reveal myself."[6]

### The Birth of Bitcoin

From this primordial stew of technologist, university researchers, cryptographers, a love of privacy in communication and in financial transactions, and a general mistrust of central authorities an anonymous, short (9 pages), but groundbreaking paper, was mailed to the Cypherpunk mailing list in 2008[4] by Satoshi Nakamoto, fittingly an alias, describing an electronic currency,nBitcoin, based upon cryptographic principals akin to asymmertric encryption, one-way functions, but in reverse.  While Bitcoin was not the first digital currency created, it was the first to solve the problem of double spending and the first to do it without the need for a central authority regultating the transaction.


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
[12]:   https://www.gchq.gov.uk/sites/default/files/document_files/CESG_Research_Report_No_3006_0.pdf "The Possibility of Secure Non-Secret Digital Encryption"