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
