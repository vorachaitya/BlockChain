# BlockChain

**Why to study Blockchain?**

- It is a disruptive technology, i.e,it has the power to change a traditional approach into a new enhanced technology.
- It has gained trust of people after financial crisis of USA in the year 2008.

**What is Blockchain?**

Blockchain is a distributed immutable ledger which is completely transparent.

**Application of Blockchain**

- Product Tracking
- Smart Contract
- International Wire Transfer
- Healthcare System

**Hashing Algorithm**

- Each block is identified by it's own unique **_hash_**.Each block also stores hash of the previous block known as **_prev hash_**.Prev hash of the first block(genesis block) is always _0_.
- Hashing is done using **_SHA256_** algorithm.The entered data is encrypted using this algorithm.It has 64 hexadecimal chahracters each of 4 bits.So,in total it has 64\*4=256 bits.

* Five requirements of hashing algorithm are as follows:
  > - **One way** :We can convert original data to encrypted data but vice versa is not possible.
  > - **Deterministic** :Whenever we give a particular input data,it should produce the same output for that particular input data. The output shouldn't change even if we run it for multiple times.
  >
  > * **Fast Computation** :The algorithm should be fast else entire time would be spent just in hashing instead of building the blockchain.
  > * **Withstand collisions** :It shouldn't be hacked easily.
  > * **Avalanche Effect** :If we make even small change in input,the hash should change for the new input data,i.e,no two inputs should have the same hash.

**Immutable Ledger**

Since blockchain is distributed network,let's suppose we have A<-B<-C<-D<-E chain.Now if a hacker attacks 'C',then hash of 'C' will change.Since 'D' is linked to prev hash of 'C' and since hash of 'C' has been changed,due to avalanche effect,now 'D' cannot match new hash of 'C' with old original hash.Thus,due to avalanche effect,'D' and 'E' will be corrupted.This will soon be known by other computer as it is distributed network,and the corrupted chain will be restored to original data by other computers.Thus attack by hackers would be saved.

**Distributed P2P network**

P2P stands for peer to peer network.If centralised network is used,then hacker can easily hack the entire network at once and leak all the data. But since in P2P network,data is held by various peers,thus it becomes difficult for hacker to hack all the data at once.

Now let's suppose hacker hacks all blocks CDE of chain A<-B<-C<-D<-E of peer 'M'.'M' has peers with 'N','P','Q'. Since 'M' has different chain then it's peers 'N','P','Q' as it is hacked, and since peers N,P,Q are in majority,thus 'M' has to chamge it's chain back to it's original form and hacker can no longer hack the chain.

**Blockchain Mining**

Blockchain mining creates an environment of trust and security.
It's shown using following steps:
Transaction->Solve Mathematical problem->Miner solved problem first->Miner verify the validity->Block is added
