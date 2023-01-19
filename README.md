## Introduction

This repository contains all the basic knowledge required to study BlockChain.It is divided into three modules namely: Blockchain,Cryptocurrency and Ethereum.

## Module A:Blockchain

#### Why to study Blockchain?

- It is a disruptive technology, i.e,it has the power to change a traditional approach into a new enhanced technology.
- It has gained trust of people after financial crisis of USA in the year 2008.

#### **What is Blockchain?**

Blockchain is a distributed immutable ledger which is completely transparent.

#### **Application of Blockchain**

- Product Tracking
- Smart Contract
- International Wire Transfer
- Healthcare System

#### **Hashing Algorithm**

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

**Consensus Protocol**

**_Proof of work_**:When miner wants to add a block to to the chain,it has to first solve a mathematical problem which is too complex,time consuming,consumes lot of electricity.It it solves it successfully,it is rewarded with a bitcoin. Now,other peers also verify this block before adding to their chain whether it has followed all the rules of mining correctly or not.If yes,then miner is again awarded with the incentive. Thus,if miner has to take utmost care while mining and it cannot perform any malicious activity because if caught,it won't get any reward or incentive amd will have to bare loss.Thus,solving mathematical problem is proof of work.Verification of new block by peer network is fast and not time consuming.

**_Longest Chain Rule(Competing Chain Problem)_**:It will accept only those blockchain which will have the longest blockchain.Thus,whichever network has longest blockchain will be considered valid and blockchain of other network will be discarded.

The Consensus Protocol of Blockchain is much better than the Byzantine Fault Tolerance as Consensus Protocol only needs a 51% majority while Byzantine Fault Tolerance needs approximately 66%.All the transaction in the Orphan block will be dropped and the miner that had mined will not get any reward.So that's why wait for the 6 confirmations before assuming payment to be successful.

# **_Module B:Cryptocurrency_**

**What is Bitcoin?**

Bitcoin is the first cryptocurrency to be invented in the year 2008.Blockchain is a technology whereas Bitcoin is a protocol that tells us how to work on blockchain as a technology,i.e,when miners should be rewarded,which consensus protocols should be followed,etc.

**What is Bitcoin's Monetary Policy?**

It is necessary to maintain the supply of money.Supply cap of Bitcoin is 21 million.Bitcoin uses Halving technique,i.e,every 4 years the new number of bitcoins that can be produced are half the number than those before 4years.Thus,no more bitcoins can be produced after the year 2140.Block frequency states that on an average,it will take 10 minutes to create a new block.

**How Mining works:The Nonce**

The hash of the block is generated when we add block number,data and prev hash in the SHA256 algorithm which gives us the hash of the block.Mathematical problem to be solved by the miner is to generate this hash,i.e, miners are given a target value. They have to generate hash in such way that it is less than or equal to the given target value. If hash is not less or equal to target value,then block cannot exist and miner cannot mine the block.If they reach the target value,then block is mined successfully.

Nonce is responsible for generating the hash.Different values of nonce have different hash values,out of which one hash value of some nonce will match the target value and block will be mined successfully.Now,we will add nonce along with block number,data and prev hash in the SHA256 algorithm which will gives us the hash value of the block.Thus,nonce simply is a mathematical number which miners use to solve a mathematical problem.When they find a nonce that reaches the target value,mining is stopped and block is added successfully.

**_Target_** :Target is a number used in mining.It is a number that block hash must be below for the block to be added on to the blockchain.The target adjusts every 2016 blocks(roughly two weeks) to try and ensure that blocks are mined once every 10 minutes on average.

**CPU vs GPU vs ASIC**

Hash rates are as follows:

> - CPUs < 10 MH/s
> - GPUs < 1 GH/s
> - ASIC > 1000 GH/s

**Mining Pools**

Mining pool creates a pool of miner's network where they together solve a problem.Thus,mining power of each individual increases by which they can now compete with big miners in the market.Also those individuals who don't know mining can be a part of the mining pool by paying a minimal fee.Also if a mining network has earned a reward,reward won't be split equally amongst it's miners.Reward would be distributed based on the hashing power of every individual of the mining pool,i.e, miner with more hashing power gets more reward because it has generated more hashes to meet the target thereby contributing more.

Also,the different network don't work on the same mathematical problem else even if one network solves the problem,it will get rewarded and the power,electricity of other networks(mining pools) would be wasted.Instead,every network(mining pool) is assigned a range of nonce and they solve mathematical problem based by changing nonce in that range only.

**Nonce Range**

Nonce is a 32 bit number.

> - Range of Nonce is 0 to 2^32-1=0 to 4x10^9(4 billion).
> - Thus,we can produce 4 billion hashes with help of 4 billion Nonce.
> - Total number of possible hashes is 64^16=10^77.
>   Thus,we have 10^77 possible hashes but we can only generate 4 billion nonces.

So what the miners do when all the nonce get exhausted and miners have not hit the target?
To avoid the above problem,we introduce a new field called "Timestamp" in our block.

**_Timestamp_**: Now, timestamp along with nonce,block number,data and prev hash is added in the SHA256 algorithm which gives us the hash of the block.Timestamp calculates time from the time when unit was created.Thus, it keeps on changing every second and since it is also passed in SHA256 algorithm,thus the hash generated also keeps on changing every second.

A miner exhausts 4 billion nonce in 40sec.Thus,it will exhaust 0.1 billion nonce in 1sec.After 1sec,all the nonce that have exhausted previosuly can again be reused as the timestamp has changed.Thus,due to avalanche effect,the hash generated would be different and can be used to match the target.

Current hashing rate is 180 million trillion hashes/sec.Therefore, 4x10^9 nonce will be covered in = (4x10^9)/(10^6x10^12)= 4x10^-9 sec which is less than 1sec.Thus before even timestamp changes(after 1sec),all the nonces have been exhausted by the miner.

So what should miner do till 1sec is reached? Should they wait for timestamp to change?

**Mempool**: Mempool is that area where all unconfirmed transactions are present.Thousands of transactions can be done in mempool.Miners pick transactions from these area and then mine to add them in the blockchain.
Every transaction has a transaction id and fees that we have to pay to miners. Thus,miners will choose those transactions first for mining which pay them more fees.

Once miner picks a transaction,let's say it has picked 4 transactions,then it adds all those picked transactions to the data filed in it's own block.Now,it first mines the transaction with highest fee in the transaction field of it's block.But as we know,it exhausts all the nonces in less then 1sec.

So what should miner do till 1sec is reached? Should they wait for timestamp to change?
No,now it will replace the transaction with lowest fee in the transaction field of it's bock with the transaction with fee just lower than the transaction with lowest fee in the transaction field.As it has replaced a transaction,due to avalanche effect,the hash will be changed and miners can now use all the nonces again without waiting for the completion of 1sec.It will keep repeating this process till timestamp changes.Once timestamp changes,it will replace the transaction with lowest fee in it's block with transaction(present in mempool but not miner's block) of highest fee.Again,same process will be repeated.

If fee paid to miner is very less,then no miner will pickup that transaction and after 72 hours,that transaction will be removed from mempool.Thus,that transaction will never be confirmed.

**Transaction and UTXOs**

UTXOs stnad for "Unspent Transaction Output".Let's us understand with an example:
The following are UTXOs:

> - Arjun -> Me 0.4 BTC
> - Raj -> Me 0.3 BTC
> - Alice -> Me 0.7 BTC
> - Bob -> Me 0.3 BTC

Now let's suppose I want to buy a coffee of 0.5 BTC.So,I will choose UTXO of Alice.0.5 BTC will be spent for coffee and remaining 0.2 BTC will be returned back to me.Thus,updated UTXOs are:

> - Arjun -> Me 0.4 BTC
> - Raj -> Me 0.3 BTC
> - Bob -> Me 0.3 BTC
> - Me -> Me 0.2 BTC

But in actual,I get only 0.1 BTC.The remaining 0.1 BTC is spent in the form of Transaction fee.Transaction fee is given to miners.Thus,the actual UTXOs are shown below:

> - Arjun -> Me 0.4 BTC
> - Raj -> Me 0.3 BTC
> - Bob -> Me 0.3 BTC
> - Me -> Me 0.1 BTC

**Cryptocurrency Wallets**

Now,how does blockchain calculate the total currency that u are holding?

It checks all those transactions in which I am recieving BTC. Example: Arjun gave me 0.4 BTC.In similar way,it calculates other transactions in which I am recieving money and sums it up.Thus,now we have 1.1 BTC(addition of all).Care is taken that those transactions which are already used up are not counted and those transaction in which I am paying money(Me -> Coffee 0.5 BTC) is also not counted.

**Private key and Public key**

![keys](https://user-images.githubusercontent.com/90527884/212564511-1222f1f1-089f-4432-a89a-ae9e1a3952b3.jpg)

**SegWit: Segregated Witness**

The size of a block is 1MB.If we increase the size of block,then it will acquire larger bandwidth to travel.It will occupy more space and the system will slow down.
Image
Now,we sent signature and public key seperately.Thus,space is saved in the block and more transactions can be accomodated in the block.
![SegWit](https://user-images.githubusercontent.com/90527884/212564818-a06a7d3e-5d8a-4d7a-b22b-48f02c3ddbd5.jpg)

**Public Key vs Bitcoin address**

Public key is used if user wants to send bitcoin to someone.

Bitcoin address is derived from public key using SHA256 algorithm.It is used if a user wants to accept bitcoin from someone.It was created so that hackers cannot hack public key and generate private key from it.Thus,it adds an extra layer of security.
![Bitcoin_address](https://user-images.githubusercontent.com/90527884/212564831-d438364e-1fd8-4a0c-9c1d-0193e9a50b2e.jpg)

**HD: Hierarchical Deterministic Wallets**

It is easy to track down bitcoin address.Thus,concept of HD wallets was introduced.
![HD_Wallet](https://user-images.githubusercontent.com/90527884/212564870-81340f84-d3ac-42a0-9cb2-fb32692a6b83.jpg)

# **_Module C: Ethereum_**

Ethereum is an open-source blockchain-based platform.It was invented by "Vitalik Buterin".Just like bitcoin,ethereum provides us with ether with which we can do transactions.

**Ethereum Nodes**

> **Full Node**: It locally stores an entire copy of blockchain and is responsible for verification and validation of blocks.Generally,miner is called Full Node.

> **Light Node**: Those nodes who don't have much storage and just want to perform transactions are called as Light Node.It stores only the block header and is dependent on full node.It is for low capacity devices which cannot afford to store gigabytes of data.

> **Archive Node**: It stores everything kept in the full node and built an archive of historical data.Thus,it requires terabytes of diskspace.

**Ethereum Account**

An Ethereum account is an entity with an ether(ETH) balance that can send or recieve transactions on Ethereum.

Types of Ethereum accounts:

> - **Externally Owned Accounts(EOA)**: EOA account is created as soon as we create a wallet.Private key helps to open the wallet.EOA allows us to check balance,send/recieve transaction,smart contract.

> - **Contract Account(CA)**: It is controlled by Contract code.

![EOA vs CA](https://user-images.githubusercontent.com/90527884/212632838-c0afe0bc-5789-4316-9a8b-1afc2c67a326.jpg)

**Smart Contract**

It is a program that runs on our Ethereum blockchain.

**Turing complete** means we can write the logic in our program whereas **Not Turing complete** means we cannot write logic in our program.We can implement concept of loops in Turing complete whereas we cannot in Not Turing complete.

Why can we use smart contract in Ethereum but not in Bitcoin?

Bitcoin uses Bitcoin script which is Not Turing complete whereas Ethereum uses Solidity which is Turing complete.Thus,we can use smart contract in Ethereum but not in Bitcoin.

Each node has following:

> - Current state of all smart contracts.
> - History of both transactions and smart contract.

**Decentralized Applications: Dapps**

Those applications which run in decentralized manner in the form of P2P network are known as decentralized applications.Dapps are made using smart contract+front end.Smart contract work as backend.

![Decentralised_apps](https://user-images.githubusercontent.com/90527884/212640074-5761600f-dce7-49ab-ae91-6cbc2802e211.jpg)

**Ethereum Virtual Machine(EVM):** Whenever we run a decentralised application,it doesn't run directly on our computer instead it runs on EVM.This EVM doesn't have access to our computer and thus cannot steal any data from our computer.Thus,our system is protected from attack of virus and hackers.

**Ethereum Gas**

If we want to run some smart contract/transaction on our Ethereum Blockchain,then ethereum gas is required.Any transaction that modifies the blockchain costs gas.The user that generated the transaction pays for the gas.Community has already assigned gas values to perform operation.Each different operation has it's own assigned gas value.Example:

> - Addition has 3 gas
> - Subtraction has 3 gas
> - Equal to has 3 gas

If operation is 10+3-6=?
Thus,total gas required is 3+3+3=9 gas

**Gas Price:** It is the amount the sender wants to pay per unit of gas to get the transaction mined.gasPrice is set by the sender.The higher the gas price,the faster the transaction will be mined.It is just like the transaction in Bitcoin.

Gas prices are denoted in gwei.(1 gwei=10^-9ETH)

**Gas Limit:** It is the maximum gas the transaction can consume.It is set by the sender.
Let say A wants to send B 2ETH.So what will be the total fees that A has to pay?

A sets the gas price per unit=100 gwei.Transaction gas limit=21,000 units.

> - Case 1:When transaction gas limit is 21,000 units.
>   Total fee will be:Gas units(limit)xGas price per unit
>
> * Total fee will be:21,000x100=210,0000 gwei or 0.0021 ETH

> - Case 2:When gas transaction limit is less than 21,000 units,i.e,
>   Transaction gas limit=20,000 units.
>
> * Therefore,transaction will be failed.

> - Case 3:When gas transaction limit is greater than 21,000 units,i.e,
>   Transaction gas limit=22,000 units.
>
> * 22,000-21,000=1,000 units will be returned

**Decentralized Autonomous Organisation(DAO):** DAO is a program written on smart contract.If there are few things that repetitive in nature and which doesn't require much logic,then we can simply add them in smart contract.It will work exactly same as an organisation and will also maintain a heirarchy.It works on it's won and there is no human intervention.Thus,it is an autonomous organisation.

![DAO](https://user-images.githubusercontent.com/90527884/212657647-d5f67da0-c5af-4fa8-accc-0510bcff1e40.jpg)

**Hard Fork:** During a hard fork,software implementing a protocol and its mining procedures is upgraded.Once a user upgrades their software,that version rejects all transactions from older software,effectively creating a new branch of the blockchain.However,those users who retain the old software continue to process transactions.Changes made here irreversible.

![hard_fork](https://user-images.githubusercontent.com/90527884/212661502-592f256f-3a0d-4ef3-b6d2-af65c57dcccb.jpg)

**Soft Fork:** Soft forks are a change to protocol,but the end product remains unchanged.A soft fork is a backward-compatible upgrade,meaning that the upgraded nodes can still communicate with the non-upgraded ones.Old nodes(not upgraded nodes) could still validate blocks and transactions(the formatting didn't break the rules),but they just wouldn't understand them.

![Soft_fork](https://user-images.githubusercontent.com/90527884/212682604-00f7b3f3-5934-45eb-a9bc-40076dd172d0.jpg)

**Initial Coin Offering(ICO):**

![ICO](https://user-images.githubusercontent.com/90527884/212683935-a3f47fe5-a3c5-4800-969a-3da8f79db4e2.jpg)

**ETH 2.0**

> - It is scalable,i.e,more number of nodes can be added to the blockchain as compared to ETH 1.0
> - It is more secure because since more number of nodes can be added,therefore before adding a block,it will be verified by those extra nodes as compared to ETH 1.0
> - It is more sustainable as the energy consumption is low.

Two major upgrades of ETH2 are Proof of stake(POS) and Sharding.

**Proof of stake(POS):** Here,there are no miners present.Instead,there are validators.If a person wants to become a validator,he has to keep certain amount of his ethers at stake and give it to the system.Minimum stake is 32 eth.

If a validator performs attachtation(attaching blocks together) correctly,then he given back his eth+transaction fee.But,if he tries to do some malicious activity,then he won't get his ether(kept at stake) back and not get any transaction fee as well.

If there are 5 persons let's say A,B,C,D,E who want to become validator,then system will randomly select a person and make him validator.Those person who will keep more ether at stake has higher chances of being selected randomly as validator.

![POS](https://user-images.githubusercontent.com/90527884/212688850-f4860ef0-cd5f-46ea-b337-2c9ff4423466.jpg)

**Sharding:** In consensus protocol,lot of time of miners was wasted in verifying and validating blocks mined by other miners.Thus,the efficiency of miners decreased and less number of transactions could be done per second.

Instead,in sharding,we divide database/blockchain into smaller subsets.Thus,now miners had to validate only that part of database/blockchain instead of entire complete blockchai.This reduced the workload on miners and now,they can give more time on mininig and larger number of transactions could be processed per second.

Major benefits of sharding:

- Transactions per second increases.
- Powerful and expensive computers will not be needed.
- More validators will join.
- Energy consumption will reduce.

**AltCoins:** All cryptocurrency available in market except Bitcoin are termed as "Altcoins".AtCoins are coins other than Bitcoins.Example: LiteCoin,Theta,BinanceCoin.
Ethereum and BinanceCoin were the largest altcoins by market capitalization as of 2021.
